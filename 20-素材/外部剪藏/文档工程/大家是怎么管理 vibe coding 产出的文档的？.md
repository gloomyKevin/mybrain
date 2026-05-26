---
title: "大家是怎么管理 vibe coding 产出的文档的？"
source: "https://linux.do/t/topic/1376900/18"
author:
  - "[[z1056544889]]"
published: 2025-12-30
created: 2026-04-22
description: "还没仔细研究过 claude.md，现在看来这东西还挺有用的"
tags:
  - "clippings"
---
还没仔细研究过 claude.md，现在看来这东西还挺有用的

---

## Comments

> **zhedream** · [2025-12-30](https://linux.do/t/topic/1376900/14?u=gloomykevin)
> 
> ![](https://linux.do/user_avatar/linux.do/z1056544889/48/1528021_2.png) z1056544889:
> 
> > 
> > 如题，在 AI 开发的时候会产出很多文档，大家都是怎么归类的？
> 
> 好的代码是不需要注释的，代码即注释。
> 
> 好的代码是不需要文档的，代码即文档。
> 
> 文档多了也是屎山。最后用也不会用。
> 
> 代码 > 注释 > CLAUDE.md（摘要与注意事项） > 文档
> 
> 能不写文档就不写，我都是把 CLAUDE.md 当作摘要，这个特别好使，claude 每次读取相关文件，如果路径下有 [CLAUDE.me](http://claude.me/) 就会自动加载。
> 
> [![image](https://cdn3.linux.do/optimized/4X/d/f/0/df0ee28ebd5722fe2d8583af96f6235770cbbe9e_2_677x500.png)
> 
> image1067×787 56 KB
> 
> ](https://cdn3.linux.do/original/4X/d/f/0/df0ee28ebd5722fe2d8583af96f6235770cbbe9e.png "image")
> 
> 当然不是说文档彻底不用，但 AI 基本不会去看的，看了也是浪费上下文。一般是我主动投喂的  
> 
> [![image](https://cdn3.linux.do/original/4X/a/f/3/af3bbabfbb7b8be37719f5f08dfe955bdcf4bbfa.png)
> 
> image928×541 54.4 KB
> 
> ](https://cdn3.linux.do/original/4X/a/f/3/af3bbabfbb7b8be37719f5f08dfe955bdcf4bbfa.png "image")
> 
> 这是我之前给他安排的流程（也是我自己工作流）
> 
> 结果就是，知识点那一点，这一点，各种冗余重复，到头来，还是得自己维护，几百行的文字，我也压根不想看，最后都是发现下 CLAUDE.md 摘要还不错。
> 
> CLAUDE.md 还有作用域，根据需要，写到不同目录的 CLAUDE.md ，而不是全部在项目根目录的 CLAUDE.md
> 
> [![image](https://cdn3.linux.do/original/4X/a/0/e/a0e69a76880d307cd1c2d1bdcf9020c7eeab7e9c.png)
> 
> image890×437 14.6 KB
> 
> ](https://cdn3.linux.do/original/4X/a/0/e/a0e69a76880d307cd1c2d1bdcf9020c7eeab7e9c.png "image")

> **wren** · [2025-12-30](https://linux.do/t/topic/1376900/15?u=gloomykevin)
> 
> 讨论要不要都行吧， 我现在是 需求、设计文档、计划 ， 每次开发完的计划我就删了。

> **z1056544889** · [2025-12-30](https://linux.do/t/topic/1376900/17?u=gloomykevin)
> 
> 嗯，这种一般也会删掉的，只是让他放到指定的地方，好管理

> **YMuxing** · [2025-12-30](https://linux.do/t/topic/1376900/18?u=gloomykevin)
> 
> 一般他产出文档我都直接删了，一堆废话  
> 最后差不多了开新对话，让他整体索引项目进行分析，让他生成 2 个文档，一个架构一个整体的 readme

> **clenlu** · [2025-12-30](https://linux.do/t/topic/1376900/19?u=gloomykevin)
> 
> 不让产出文档 多人写作 让 ai 总结下项目就好了 那么多文档也没人愿意看 而且还像是在项目里拉屎

> **Waviness6884** · [2025-12-30](https://linux.do/t/topic/1376900/20?u=gloomykevin)
> 
> 你这个倒是严谨，我都是让放 docs 目录下

> **wren** · [2025-12-30](https://linux.do/t/topic/1376900/21?u=gloomykevin)
> 
> 对，我是制定了一个目录下面分了需求、设计文档、计划。还有参考资源。 文档分别在这个几个目录中。