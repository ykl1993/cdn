# iOS SDK开发指南 {#concept_kh4_glk_xdb .concept}

本文档介绍了MAC iOS SDK的使用方式。

**说明：** 集成前可参考[移动加速 iOS Demo](https://github.com/aliyun/alicloud-ios-demo/tree/master/mac_v2_ios_demo?spm=a2c4g.11186623.2.13.buLg2S)。

## SDK集成 {#section_oj5_bmk_xdb .section}

-   指定Master仓库和阿里云仓库：

    ```
    source 'https://github.com/CocoaPods/Specs.git'
    source 'https://github.com/aliyun/aliyun-specs.git'
    ```

-   添加依赖：

    ```
    pod 'AlicloudMAC', '~> 1.0.0'
    ```


## SDK使用 {#section_mxj_cmk_xdb .section}

**说明：** 移动加速SDK内部Log查看Tips：可通过过滤字段`[MAC`查看。

1.  获取加速示例并初始化。

    `AppKey`和`AppSecret`可在 [App列表页](https://ams.console.aliyun.com/?spm=a2c4g.11186623.2.14.buLg2S#/productList) 获取。

    ```
    AlicloudMACService *service = [AlicloudMACService sharedInstance];
    [service initWithAppKey:@"******" appSecret:@"******" callback:^(BOOL res, NSError *error) {
        if (res) {
            NSLog(@"MAC SDK init success.");
        } else {
            NSLog(@"MAC SDK init failed, error: %@", error);
        }
    }];
    ```

2.  加速请求配置。
    -   若原生网络请求基于 NSURLConnection 或者 NSURLSession（session对象通过`sharedSession:`获取）发出，SDK可自动拦截原生网络请求，走到加速链路。
    -   若原生网络请求基于 NSURLSession（session对象配置有自定义NSURLSessionConfiguration），需注册移动加速的 MACURLProtocol，如下所示：

        ```
        NSURLSessionConfiguration *configuration = [NSURLSessionConfiguration defaultSessionConfiguration];
        configuration.protocolClasses = @[ [MACURLProtocol class] ];
        NSURLSession *session = [NSURLSession sessionWithConfiguration:configuration];
        ```

    -   移动加速SDK是通过注册 NSURLProtocol 拦截网络请求，需要注意 NSURLProtocol 的注册顺序。多个 NSURLProtocol 注册后，网络请求拦截为注册的相反顺序。移动加速 MACURLProtocol 的注册时机为`SDK初始化`时，调用`停止`和`重启`接口时，分别为`注销`和`重新注册` MACURLProtocol。
    -   示例：

        ```
        [[AlicloudMACService sharedInstance] initWithAppKey:testAppKey appSecret:testAppSecret callback:^(BOOL res, NSError *error) {
            if (res) {
                /* HookURLProtocol注册在SDK初始化之后，因此HookURLProtocol先拦截到网络请求 */
                [NSURLProtocol registerClass:[HookURLProtocol class]];
            }
        }
        ```

3.  自定义降级策略
    -   用户可设置降级策略，满足降级条件的网络请求，降级走原生网络库链路。
    -   基于下述接口配置：

        ```
        - (void)setDegradationPolicy:(id)delegate;
        ```

4.  停止和重启移动加速。
    -   调用步骤 1所示的初始化接口，并按照步骤 2完成配置后，原生网络请求可自动被拦截，走到加速链路。
    -   调用停止接口，停止网络请求拦截。

        ```
        /**
         停止移动加速
         */
        - (void)stop:(MACCallbackHandler)callback;
        ```

    -   调用重启接口，重新恢复网络请求拦截。

        ```
        /**
         重启移动加速
         */
        - (void)restart:(MACCallbackHandler)callback;
        ```

5.  如何查看网络请求是否加速成功？
    -   打开移动加速SDK Log。
    -   SDK初始化成功后，发出网络请求，可看到如下日志：

        ```
        [MACURLProtocol]-[I]: URL: [https://xxx.xxx.com/xx], accelerate type: [2]
        [MACURLProtocol]-[D]: Start loading request: <NSMutableURLRequest: 0xxxxxxxxxxxxx> { URL: https://xxx.xxx.com/xx }
        ```

    -   网络请求结束后，可查看到如下日志，

        -   `request result`
            -   1：网络请求成功
            -   0：网络请求失败
        -   `accelerate result`
            -   1：网络请求加速成功
            -   0：网络请求加速失败
        ```
        [MACACCSNetworkRequest]-[I]: [https://xxx.xxx.com/xx] request result: [1], accelerate result: [1]
        ```


## API接口 {#section_a5k_cmk_xdb .section}

```

/**
降级策略定义
*/
@protocol MACDegradationDelegate 
- (BOOL)shouldDegrade:(NSString *)hostName;
@end
/**
SDK回调Handler定义
@param res 回调结果
*/
typedef void (^MACCallbackHandler)(CallbackResult *res);
/**
SDK初始化并开启移动加速
@param appKey AppKey
@param appSecret AppSecret
@param callback 回调
*/
- (void)initWithAppKey:(NSString *)appKey
appSecret:(NSString *)appSecret
callback:(MACCallbackHandler)callback;
/**
设置自定义降级策略
@param delegate 降级策略
*/
- (void)setDegradationPolicy:(id)delegate;
/**
停止移动加速
*/
- (void)stop:(MACCallbackHandler)callback;
/**
重启移动加速
*/
- (void)restart:(MACCallbackHandler)callback;
/**
日志开关
@param enabled YES: 打开; NO: 关闭（默认）
*/
- (void)setLogEnabled:(BOOL)enabled;
```

## 示例 {#section_cjt_fpk_xdb .section}

```

/**
初始化MAC SDK
*/
- (void)initMACSDK {
AlicloudMACService *service = [AlicloudMACService sharedInstance];
[service setDegradationPolicy:(id)self];
[service initWithAppKey:@"******" appSecret:@"******" callback:^(BOOL res, NSError *error) {
if (res) {
NSLog(@"MAC SDK init success.");
} else {
NSLog(@"MAC SDK init failed, error: %@", error);
}
}];
}
/**
自定义降级策略
@param url 请求URL
@return YES: 降级到原生网络库; NO: 不降级
*/
- (BOOL)shouldDegrade:(NSURL *)url {
/* 若请求Host为a.b.com，降级走原生网络库 */
if ([[url host] isEqualToString:@"a.b.com"]) {
return YES;
}
return NO;
}
static NSURLSession *_session;
/**
发网络请求
*/
- (void)sendNetworkReqeust {
static dispatch_once_t onceToken;
dispatch_once(&onceToken, ^{
/* 若基于NSURLSession发网络请求并配置SessionConfiguration，需要注册MACURLProtocol */
if (!_session) {
NSURLSessionConfiguration *configuration = [NSURLSessionConfiguration defaultSessionConfiguration];
configuration.protocolClasses = @[ [MACURLProtocol class] ];
_session = [NSURLSession sessionWithConfiguration:configuration];
}
});
NSURL *url = [NSURL URLWithString:@"xxxxxx"];
NSURLRequest *request = [NSURLRequest requestWithURL:url];
NSURLSessionDataTask *task = [_session dataTaskWithRequest:request completionHandler:^(NSData * _Nullable data, NSURLResponse * _Nullable response, NSError * _Nullable error) {
if (error) {
NSLog(@"Error: %@", error);
return;
}
NSLog(@"Content: %@", [[NSString alloc] initWithData:data encoding:NSUTF8StringEncoding]);
}];
[task resume];
}
```

