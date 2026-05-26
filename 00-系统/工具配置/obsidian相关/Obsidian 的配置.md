
正好最近我也在研究这方面。感觉 Obsidian + Agent 最灵活啊，以后改结构也就是改改 skill 和脚本文件。

获取知识方面，你说的这几个链接我感觉挺好爬的啊。Bilibili api 接口网上一大堆，反爬没怎么做。微信公众号用浏览器过验证或者有个邪修带上微信的请求头能直接 curl。博客文档就更简单随便抓了。pdf 用 make 或者 mineru ocr 变成 md 文档

  知识库构建讨论：https://linux.do/t/topic/1956732

可以把抓取写成 skill 加脚本，然后让:lobster:或者 Hermes 去抓，然后存到你的知识库

生成摘要、存到哪里可以都总结成工作流

之前我还自己写过脚本，发给 tg 然后他自己调 api 总结发到我的 github 笔记库，现在有 Hermes 直接用 Hermes 了都

  

知识库配置：

https://linux.do/t/topic/1408512

  

https://sspai.com/post/104619

  
【图床】
github：https://juejin.cn/post/7597276695403544617

讨论帖：https://forum-zh.obsidian.md/t/topic/58234/10
优质回答摘录：
全站免费方案：  
我用的是一个基于 CloudFare 免费计划部署的图床项目，这是作者的教程网站 [https://cfbed.sanyue.de 12](https://cfbed.sanyue.de/)，里面详细讲述了如何部署。另外还有一位开发者基于这个图床项目开发了 Obsidian 插件，[https://github.com/fantasy-ke/obsidian-cf-imgbed/tree/1.0.2 15](https://github.com/fantasy-ke/obsidian-cf-imgbed/tree/1.0.2)。存储渠道有多种选择，我用的是 Telegram 的渠道，因为这个渠道没有存储限制，不过单个文件上传限制是 20 MB，但作者通过文件切片上传解决了这个问题，我上传过 800~900 MB 的视频都可以，超过 1G 就不行了。使用的时候不需要科学上网。插件在文档中直接粘贴图片就可以自动上传并转换为 MarkDown 格式，不过对于已有的附件无法自动转化，插件里还保留了本地备份功能可选择路径和是否开启还有上传时图片添加水印的功能。图床项目部署的网站有访问码，可以防止被别人滥用。插件移动端也可以使用。

开源项目：https://cfbed.sanyue.de/

![20260316-173143.jpeg](https://b653a527.cloudflare-imgbed-akv.pages.dev/file/1776842471316_20260316-173143.jpeg)

图片上传测试