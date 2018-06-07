# Android SDK开发指南 {#concept_wf4_jpk_xdb .concept}

## 前言 {#section_qmj_ypk_xdb .section}

本文旨在介绍MAC Android SDK的接入步骤和使用方法。

## 安装 {#section_ibs_zpk_xdb .section}

1.  配置maven仓库。

    `build.gradle`添加阿里云maven仓库。

    ```
    allprojects {
        repositories {
            maven {
                url "http://maven.aliyun.com/nexus/content/repositories/releases"
            }
        }
    }
    ```

2.  配置gradle依赖。

    ```
    dependencies {
        compile 'com.aliyun.ams:alicloud-android-mac:1.0.0'
    }
    ```

    目前MAC android sdk只支持arm架构，建议用真机进行测试。

3.  Manifest配置。
    1.  添加组件。

        ```
        <service
                    android:name="anetwork.channel.aidl.NetworkService"
                    android:exported="false">
                    <intent-filter>
                        <action android:name="anetwork.channel.aidl.IRemoteNetworkGetter" />
                    </intent-filter>
                </service>
        ```

    2.  添加权限。

        ```
        <uses-permission android:name="android.permission.INTERNET" />
            <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
            <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
        ```

4.  Proguard配置。

    ```
    -keep class com.aliyun.ams.** {*;}
    -keep public class org.android.spdy.** {*;}
    -dontwarn com.alibaba.**
    -dontwarn com.taobao.**
    -dontwarn anetwork.channel.**
    -dontwarn org.android.**
    ```


## 支持的版本 {#section_why_zpk_xdb .section}

mac sdk支持的android最小版本为`10`。

```
minSdkVersion 10
```

## API {#section_xzy_zpk_xdb .section}

-   MacClient

    MacClient主要用来发起请求`Request`和得到响应`Response`，使用方法参见[最佳实践](cn.zh-CN/用户指南/业务类型/类型6：移动加速/Android SDK开发指南.md#section_fsz_zpk_xdb)：

    ```
    public final class MacClient {
        // 用于MAC sdk的初始化
        public static void init(MacConfig config);
        // 根据输入的Request获得一个Call对象
        public Call newCall(Request request);
        // MacClient的Builder
        public static final class Builder {
            public MacClient build();
        }
    }
    ```

-   MacConfig

    MAC sdk在初始化时需要传入全局配置MacConfig，使用方法请参考最佳实践-初始化：

    ```
    public final class MacConfig {
         // MacConfig的Builder
        public static final class Builder {
             // 设置Context
             public Builder context(Context context);
             // 设置appKey
             public Builder appKey(String appKey);
             // 设置appSecret
             public Builder appSecret(String appSecret);
             // 创建MacConfig对象
             public MacConfig build();
        }
    }
    ```

-   Request

    Request表示一个HTTP请求，每一个Request包含一个URL、method、请求header和body，使用方法请参考最佳实践-构建请求对象：

    ```
    public final class Request {
         // 返回URL
        public String url();
        // 返回method，默认为Get
        public String method();
        // 返回请求头部
        public Map<String, String> headers();
        // 返回请求body
        public byte[] body();
        // Request的Builder
        public static final class Builder {
            // 设置URL
            public Builder url(String url);
            // 设置method
            public Builder method(String method, byte[] body);
            // 设置header
            public Builder headers(Map<String, String> headers);
            // 添加header
            public Builder addHeader(String name, String value);
            // 移除header
            public Builder removeHeader(String name);
            // 构建Request对象
            public Request build();
        }
    }
    ```

-   Response

    Response表示一个Request的响应，每一个Response包含状态码、响应头部以及响应body：

    ```
    public final class Response {
         // 返回状态码
        public int code();
        // 返回响应头部
        public Map<String, String> headers();
        // 返回响应body
        public byte[] body();
        // 返回请求是否成功
        public boolean isSuccessful();
    }
    ```

-   Callback

    MAC sdk允许用户使用异步Callback的方式，正常时返回Response，异常时返回MacException，使用方法请参考最佳实践-异步请求过程：

    ```
    public interface Callback {
         // 正常时返回Response
        void onResponse(Call call, Response response);
        // 异常时返回MacException
        void onFailure(Call call, MacException exception);
    }
    ```


## 最佳实践 {#section_fsz_zpk_xdb .section}

1.  初始化。
    1.  调用`MacConfig.init`方法，设置`AppKey`，`AppSecret`，`Context`，建议在`Application.onCreate`时调用：

        ```
        public class DemoApplication extends Application {
            @Override
            protected void attachBaseContext(Context base) {
                super.attachBaseContext(base);
            }
            @Override
            public void onCreate() {
                super.onCreate();
                // 初始化MacConfig
                MacConfig config = new MacConfig.Builder()
                        .context(this)
                        .appKey(APP_KEY)
                        .appSecret(APP_SECRET)
                        .build();
                MacClient.init(config);
            }
        }
        ```

        其中，`AppKey`和`AppSecret`可在 [App列表页](https://ams.console.aliyun.com/?spm=a2c4g.11186623.2.24.CoafA8#/productList) 获取。

    2.  构造`MacClient`对象，通过该对象来进行网络操作：

        ```
        // 构造MacClient对象
        MacClient client = new MacClient.Builder().build();
        ```

2.  构建请求对象。

    请求对象`Request`可以设置`url`，`header`，`method`等，其中`method`默认为`Get`方法：

    ```
    Request req = new Request.Builder()
                                .url(url)
                                .headers(headers)
                                .addHeader("User-Agent", "Your UA")
                                .method("POST", body)
                                .build();
    ```

3.  同步请求过程。

    下面为移动加速的`同步请求`示例，**使用时请确保`同步请求`方法在`后台线程`中执行**:

    ```
    new Thread(new Runnable() {
        @Override
        public void run() {
            Response rsp = null;
            try {
                rsp = client.newCall(req).execute();
            } catch (MacException e) {
                e.printStackTrace();
            }
            if (rsp != null) {
                int statusCode = rsp.code();
                byte[] data = rsp.body();
                Log.d(TAG, "[DemoActivity] execute statusCode: " + statusCode + " data: " + new String(data));
            }
        }
    }).start();
    ```

4.  异步请求过程。

    下面为移动加速的异步请求示例，使用时请确保异步请求方法在后台线程中执行:

    ```
    new Thread(new Runnable() {
        @Override
        public void run() {
            client.newCall(req).enqueue(new Callback() {
                @Override
                public void onResponse(Call call, Response response) {
                    int statusCode = response.code();
                    byte[] data = response.body();
                    Log.d(TAG, "[DemoActivity] onResponse statusCode: " + statusCode + " data: " + new String(data));
                }
                @Override
                public void onFailure(Call call, MacException e) {
                    Log.d(TAG, e.getMessage(), e);
                }
            });
        }
    }).start();
    ```

    **如何判断加速是否成功**

    -   过滤和查看tag为`mac`的日志，例如控制台通过adb logcat -s mac来过滤。
    -   请求成功后可以看到类似日志：

        ```
        [DHandler] url: https://xxx/xxx.html AccSuccess: 1 reqSuccess: 1
        ```

    其中，AccSuccess为`1`表示加速成功，reqSuccess为`1`表示请求成功


