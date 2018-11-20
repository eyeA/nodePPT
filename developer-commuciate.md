title: 开发中常见问题的沟通
speaker: eyeseau
url: https://github.com/eyea/nodeppt
transition: zoomin
theme: moon
files: /js/demo.js,/css/demo.css,/js/zoom.js
highlightStyle: monokai_sublime
usemathjax: yes

<!-- 是什么 为什么 怎么样 -->

[slide]
---
# 开发中常见问题的沟通
<small>前端: *eyeseau*</small>

<!-- 首页 综述 -->
[slide]

# 概要
* 主要聊下，一个需求从评审到上线过程中都有哪些沟通点，侧重于开发同学和测试同学
* 希望能够通过这次的描述和讨论，我们的工作沟通能够顺畅一些，团队更和谐一点
* 欢迎大家一起讨论和补充

[slide data-transition="vertical3d"]

# 当前的业务流有哪些沟通点?
---
* 流程: 需求、沟通、文档等
* 角色: 测试、开发、产品、业务等

<!-- 几个概念 -->
[slide]

# 测试和开发: 说不完的情话
----
[slide]
# 个人理解角度来粗略的说 {:&.flexbox.vleft}
* 前端负责数据的展现以及和用户的交互；
* 而后端，负责数据的处理逻辑；
* 然后测试部分呢，既要对前端的展现交互来进行测试，也要对数据的处理逻辑进行校验，产品需求点要实现的到位，case覆盖面只能多不能少，这个工作很复杂。
[slide]
# 前端项目简介 {:&.flexbox.vleft}
<small>我们上线或者pre的时候，有时候会听到开发说，a上了，b上等等，
对于大家来说，就是一个需求，但我们可能会联动好多个项目或者是好多个服务，很多我们觉得是前端应该是两个项目，但前端来说，是一个，因为有的可以做适配进行兼容。
所以很有必要来简单介绍下前端的项目，当然我们主要说教师端。</small>
[slide]
# 教师前端项目 {:&.flexbox.vleft}
* m-abc 我们的管理后台
* teacher-abc 教师客户端 包含windows和macOs
* home-teacher 老师招聘官网的pc和移动端
* management-teacher 新老师管理后台 n
* teacher-app 我们的ios和安卓对应的前端部分

[note]
所需测试环境 a1-a9、 jenkins、 域名服务、技术支持等
感谢运维同学支持
[/note]

[slide data-transition="zoomin"]

<!-- 前端和后端 -->
# 前端和后端
---
[slide]
# 前后端配合 {:&.flexbox.vleft}
<small>我们和后端同学的配合方式很中规中矩，评审时候和产品测试一起对需求达成共同认知，定义数据结构，定义字段（这个目前是后端同学直接定义的），
他们部署到对应的后端测试环境，我们连接，然后对数据按照产品的需求进行定制化的处理，以及展现和交互，简单的来说
就是这样。这个中间有很多想要聊的。</small>
[slide]
# 大概有这么几点 {:&.flexbox.vleft}
* 比如数据结构，对于列表类的我们喜欢array;
* http请求的返回我们倾向于规范类的统一（这个我们双方也一直在去遵守），比如成功返回data  status  msg (success or  error)；
  获取展示用get ，编辑、增加信息用post ，修改用put， 删除delete；
* 字段用驼峰等等
* n
[note]
1. 有一个是我们经常会发生点小错误的是数据类型数字还是字符串，json串还是数组，默认是undefined、null，还是‘’、false、true、0等等；<br/>
2. 比如性别，开发之间喜欢0 1 2 来表示，对应关系其实也需要，哪个是未知，那个是男性，哪个是女性，然后这个值是 0 1 2 是数字还是字符串类型的。<br/>
3. 为什么纠结到这里呢，前端也在规范，值的比较，现在大部分用的是 === 而不是 == ，前者校验值以及类型，后者会自动进行类型转换。
[/note]

<!-- 前端和测试 -->
---
[slide]
# 前端、测试配合 {:&.flexbox.vleft}
<small>教师组测试同学个个都是宝，开发都喜欢，教师组测试妹子覆盖率100% 😆 🤷‍</small>
[slide]
# 例子很多 {:&.flexbox.vleft}
* n first story
* 403 token
* 404 地址
* 500 服务器
* 503
* 302
[note]
小故事: <br/>
小t发现一个bug，聪明的小t打开控制台发现有个飘红的404，拿着这个去找小b，小b说我这里没有这个问题，你去找小f；
小f一看，卧槽，请求地址写错了，然后让小t等下，马上就好；
按照文档地址一个个字拼上地址后，本地测，ok，部署到测试环境给小t看；
小t刷新下一看，特么的，还是404，开始怀疑小f是不是在应付她；
然后问小f，小f慌了，去洗了把脸，揉了揉眼再看了下代码，改了啊，地址就是这样啊，不应该啊，然后找小b，404了，怎么搞。
小b呢看了下小f苦逼的脸，拍了下脑门，老铁，我忘了部署上去了...
[/note]

[slide data-transition="zoomout"]
---
# Thank U
<small>前端: *eyeseau*</small>

