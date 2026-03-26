# PicGo

#### 介绍
Markdown 语法处理图片返回的是一个 URL 链接。

如果上传的是本地图片，则会显示文件的本地路径，既然是本地路径，分享文件时就显得极不方便了。它需要将文章中的图片一并发送，接受者还要配置本地环境与发送者图片路径一致才可看到，或者根据自己的目录，修改文章中图片路径。如果使用的是图床工具显示的是外链，可以「随时随地」查看，并不需一并发送图片，也无需自行配置本地环境。

或许上面说的过于抽象，我们设想这样一个场景：

你在 Typora 里写好一篇图文文章（为了显示差异，这篇图文采用本地图片和图床链接两种形式），然后发送这个 .md  文件给协作者进行编辑修改。
![输入图片说明](https://images.gitee.com/uploads/images/2021/1017/101843_da641475_7760175.png "屏幕截图.png")

必定不久你的协作者就会一脸疑惑，说 Ta 根本就看不到第一张图片，因为在 Ta 那里，是这样的：
![输入图片说明](https://images.gitee.com/uploads/images/2021/1017/101853_de0fb17e_7760175.png "屏幕截图.png")

如果你又不小心删除了第一张图片，那么连你也无法在 Typora 看到它了。而你试着删除使用图床外链的第二张图片，你发现仍然能够使用，实际上的效果和上图一样。

想必好奇的你一定会惊喜「图床」是什么？为什么图床会这么方便？！

图床，顾名思义就是进行图片存储的服务器，同时允许对外连接网络，所有人可以访问。

### 免费图床

免费的代价：众多免费图床服务注册条款里均有禁止商用说明，万一哪天你使用的服务挂掉了或者关闭了图片外链，那你所有的链接都无法访问了，对你造成的损失或许不小。比如，前几年的微博图床。

SMMS：稳定且快捷，是不少人主力图床的选择，同时开放 API，虽然已经推出付费套餐，但免费版本已经足够能用，不过公众号无法识别 SMMS 图床链接。

ImgURL：对游客有限制，每日最多上传 10 张，单张图片不能超过 5M，偶尔用用还是挺好的。

GitHub、Gitee：代码托管云服务网站，帮助开发者存储和管理其项目源代码，且能够追踪、记录并控制用户对其代码的修改。不同的是，GitHub 服务器在国外，Gitee 服务器在国内，访问速度更快。甚至你可以更简单粗暴地把它理解为一个巨型网盘，可以存储任何东西。

如果想要免费使用，极推荐使用这两款服务，毕竟跑路的可能性极小。

### 安装教程


PicGo 与 Gitee
既然是免费服务，首先需要建立自己的 Gitee 图床库，详细步骤如下。

新建图床仓库
![输入图片说明](https://images.gitee.com/uploads/images/2021/1017/102615_bd76278f_7760175.png "屏幕截图.png")

获取 token：点击头像，进入 个人设置 ，点击左侧「私人令牌 - 生成新令牌 - 修改私人令牌权限 - 简单私人令牌描述 - 提交」即可生成私人令牌 token。
![输入图片说明](https://images.gitee.com/uploads/images/2021/1017/102155_ebe93dd2_7760175.png "屏幕截图.png")
注意：token 只会明文出现一次，注意保密，尽量不要丢失，否则又要重新生成。

回到 PicGo。因为 PicGo 没有默认提供 Gitee 选项，所以需要通过插件开启第三方服务。首先在插件市场打开搜索 Gitee，点击任意一个，即可完成安装和所有配置。
![输入图片说明](https://images.gitee.com/uploads/images/2021/1017/102214_9ada62d1_7760175.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2021/1017/102228_9f12b3b1_7760175.png "屏幕截图.png")

### 验证

PicGo + Typora
在 Windows 平台，我更常用的 Markdown 编辑器就是 Typora 了。

Typora 是一款简洁高效、功能全面、执行优雅的全平台 Markdown 编辑器，也是目前最受欢迎本地 Markdown 编辑器之一（尤其是在 Windows 下）。它将源码编辑和实时预览合二为一，真正实现了「所见即所得」的渲染效果，给予作者极高的沉浸体验。

除了上述功能，Typora 搭配 PicGo 可以实现比 VScode（或者其他笔记工具） 写 Markdown 文章更流畅的体验了。

直接拖拽或直接将剪贴板图片粘贴进 Typora，便可实现自动上传到 PicGo 图床。实现的效果是这样的：
![输入图片说明](https://images.gitee.com/uploads/images/2021/1017/102901_86a4dfe9_7760175.png "屏幕截图.png")

打开 Typora，使用快捷键 Ctrl + , 进入偏好设置，找到「图像」修改相应设置选项。

1、插入图片勾选「对本地图片应用规则」「对网络图片应用规则」「插入图片自动转义」。
2、上传服务设定：PicGo (app)，PicGo 路径：自己主机中安装的 PicGo.exe 的存放路径。
3、点击「验证图片上传选项」。
![输入图片说明](https://images.gitee.com/uploads/images/2021/1017/102940_3ddff30a_7760175.png "屏幕截图.png")
![输入图片说明](https://images.gitee.com/uploads/images/2021/1017/102946_01411342_7760175.png "屏幕截图.png")

此时，PicGo 里多出两张图片，就说明连接成功了。
![输入图片说明](https://images.gitee.com/uploads/images/2021/1017/102957_562010d1_7760175.png "屏幕截图.png")

#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request


#### 特技

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  Gitee 官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解 Gitee 上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是 Gitee 最有价值开源项目，是综合评定出的优秀开源项目
5.  Gitee 官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  Gitee 封面人物是一档用来展示 Gitee 会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)
