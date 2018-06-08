# CDN访问日志统计与CNZZ的统计结果存在差异原因 {#concept_e2b_5f1_ydb .concept}

CNZZ的统计方式是在每个页面放置一段JS代码，当用户访问这个页面，并且页面加载成功时，JS才会统计到。假如有的页面加载失败，或者是有的页面没有放这段JS代码的话，就无法统计。另外，假如其它网站中引用该网站中的某个文件、某些图片的话，CNZZ也是无法统计到的。而CDN的统计则会更全面，我们是基于日志中的每一个访问请求统计的。还有一点不同的是，在计算PV的时候，如果同一个页面中有多个iframe标签的话，CDN计算的是多个PV。

如问题还未解决,请联系[售后技术支持](https://selfservice.console.aliyun.com/ticket/createIndex.htm)。

