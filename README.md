# ~~智慧树知到自动讨论~~

## 🔴 经研究，本脚本没有实质作用

根据 [《【问答】2022 秋冬学期问答新规则 》](https://wiki-wenda.zhihuishu.com/问答模块业务知识/【问答】2022秋冬学期问答新规则)，问答分取决于提问、回答问题的有效率，而不是数量。因此，本脚本停止更新，也请不要尝试本脚本。

以下为原介绍。

------

还在为形式主义小水课互动分不高而头疼？**为什么我苦苦回答了 139 个问题，收获了 280 个点赞，居然还只有 8 分？？？？？**

![image-20221228153507081.png](https://bj.bcebos.com/baidu-rmb-video-cover-1/6a27c6a65caa86f3d0ebb4318ac469d8.png)

不要怕，让这个脚本拯救你！让人工智能成为刺破形式主义的利剑！

它能自动回答热门问题列表中的问题（回答来自 OpenAI 开发的语言模型），并自动点赞，还可以帮你的好友给你点赞😋



## 食用教程

### 前期准备

1. 你需要准备一个 OpenAI 账户，注册方法自行研究，注册好以后在 [Account API Keys - OpenAI API](https://beta.openai.com/account/api-keys) 申请一个 `API Key` 。

   > 如果你无法访问 OpenAI ，你也可以选择其他 API 提供商，申请其 `API Key`

2. 安装 `Node.js` ，方法也自行研究吧😶‍🌫️




### 使用步骤

1. 克隆本仓库，将仓库根目录下的 `config.yaml.example` 更名为 `config.yaml` 并打开

2. 打开课程的热门讨论页面，网址应该类似这样

   ![image-20221228142757474.png](https://bj.bcebos.com/baidu-rmb-video-cover-1/70438a033a5ac7ebf7214e82301daf0a.png)

   找到自己你的课程的 `courseId` 和 `recruitId` ，填入第一步打开的 `config.yaml`

3. 将 [前期准备](#前期准备) 环节申请到的 `API Key` 填入 `config.yaml`
	
3. 选择问题来源（热门问题 `top` / 最新问题 `latest` ），填入 `config.yaml`
	
5. 想想你准备回答几题，一页是 `50` 题，将起始页数 `from` 和终止页数 `to` 填入 `config.yaml` （页数从 0 开始）

   > **如果你的问题来源为热门问题**，由于智慧树的限制，最多只能获取 3 页，即 `from` 和 `to` 都要小于等于 2

5. （可选）在课程回答页面右键，选择检查，找到 `应用程序` 选项卡，在左侧找到 `Cookie` 下的 `https://qah5.zhihuishu.com` ，在右侧找到 `jt-cas` ，将它的值填入 `config.yaml`

   > 如果你没有在这一步填入 `jt-cas`，则运行时将使用**二维码登录**
   >
   
6. （可选）如果你使用的是其他 API 提供商，请将其域名填入 `config.yaml`。这一步请查阅你使用的 API 提供商的使用手册

7. （可选）如果你有同学互相点赞刷分，可以将他们的 `jt-cas` 填入 `config.yaml` 中的 `viceWisdomtreeJtCasList` ，将会自动点赞

7. （可选）如果你想使用代理，请修改 `config.yaml` 中的 `proxy`

7. （可选）如果你的 OpenAI 账户不是付费账户，大概率会遇到 `429` 错误，这是因为 OpenAI 限制了免费帐户的请求速率，因此你可能还需要设置回答的间隔时长 `interval`

8. 保存  `config.yaml` 

9. 打开终端，导航到根目录，执行 `npm i`

10. 执行 `npm start` ，然后就好啦😋



## 注意

- 短时间内回答次数太多会触发智慧树**验证码**机制，请登录网页版智慧树人工回答任意问题，完成验证码后重新运行脚本

- 一段时间回答次数太多会被**禁言**半小时，请待禁言期结束后重新运行脚本

- 来自 OpenAI 的回答有时会少于 3 个字，请根据 `qid` 打开问题页面，手动修改答案

  > 回答字数少于 3（含）为无效回答，任何符号均不计数。 —— 智慧树



## 致谢

 - [【JS 逆向】知到 / 智慧树 加密参数逆向及 Python 实现](https://www.bilibili.com/read/cv15620703) 

- [JS NICE | Software Reliability Lab in ETH](http://jsnice.org/) 

- [luoyily/zhihuishu-tool: 知到，智慧树 API 及工具](https://github.com/luoyily/zhihuishu-tool)



## 最后

欢迎提 [issue](https://github.com/JiunnTarn/wisdomtree_auto_discuss/issues) 

