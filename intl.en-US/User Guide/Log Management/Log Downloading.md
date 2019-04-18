# Log Downloading {#concept_khc_mbf_xdb .concept}

-   You can query the log files in the Log Management within 4 hours.
-   Log files are segmented on an hour basis.
-   You can download the log files within **1 month**.
-   Name a log file based on the rule: `Acceleration domain name_year_month_date_start time_end time`.
-   Log field format description.

Sample log content

```
[9/Jun/2015:01:58:09 +0800] 188.165.15.75 - 1542 "-" "GET http://www.aliyun.com/index.html" 200 191 2830 MISS "Mozilla/5.0 (compatible; AhrefsBot/5.0; +http://ahrefs.com/robot/)" "text/html"
```

Log field description

|Field|Parameter|
|:----|:--------|
|time|\[9/Jun/2015:01:58:09 +0800\]|
|access ip|188.165.15.75|
|proxy IP|-|
|Responsetime \(Unit: ms\)|1542|
|referer|-|
|method|GET|
|access url|[http://www.aliyun.com/index.html](http://www.aliyun.com/index.html)|
|httpcode|200|
|requestsize \(Unit: byte\)|191|
|responsesize \(Unit: byte\)|2830|
|cache hit status|MISS|
|UA header|Mozilla/5.0 \(compatible; AhrefsBot/5.0; +[http://ahrefs.com/robot/](http://ahrefs.com/robot/)\)|
|File type|text/html|

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/5171/15555678753516_en-US.png)

