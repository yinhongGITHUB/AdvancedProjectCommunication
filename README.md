# 项目沟通进阶篇

### 1.沟通是什么？

​	沟通能力包含着表达能力、倾听能力和设计能力（形象设计、动作设计、环境设计）。沟通能力看起来是外在的东西，而实际上是个人素质的重要体现，它关系着一个人的知识、能力和品德。

### 2.为什么要提升沟通能力？

作为一个程序员，与人交流是不可避免地。高效的沟通方式可以提升单次沟通体验，甚至加快整个项目的进程。要知道，工作可不仅仅是敲代码那么简单。

### 3.如何去提升沟通能力？

#### 3.1偷梁换柱之偷换概念法

##### 是一种并不需要产品完全理解你的代码逻辑，却可以让他更加深入的了解产品的沟通方法。

在之前的项目研发中，有遇到这样一个问题。

问题场景：登陆页面需要一个以忘记密码为入口进而开展验证流程的需求，具体如下：

![image-20220701193551373](https://github.com/yinhongGITHUB/AdvancedProjectCommunication/blob/main/images/image-20220701193551373.png)

![image-20220701193310768](https://github.com/yinhongGITHUB/AdvancedProjectCommunication/blob/main/images/image-20220701193310768.png)

由于此时是未登陆状态，用户的一切操作都是不可信的。当输入一次图形验证码之后，所获的cid，只能允许获取一次验证码。当用户在第一次获取验证码之后，等待六十秒，再次点击获取验证码，会提示，请刷新图形验证码并验证。但是cid是不会变的，后端检测的是在获取验证码之前，有没有进行一次图形验证码的验证。

##### 那么问题来了，如何让产品心甘情愿地接受当第二次点击获取验证码时，弹出图形验证码呢？

直接说必须获取一次验证码得先获取一次图形验证码吗？如此粗暴的方式显然不是我所追求的。

这里可以用偷换概念法：跟产品说一个cid只能从短信服务那边拿到一条短信，而一个cid一旦用过就是失效了，所以再重复获取验证码时，得先去拿一次新的cid，以便接下来的流程。

但其实，我们知道，cid始终是没有变化的。不过是考虑到安全性，加了一层验证而已。

怎么样，是不是平滑很多呢?给予产品足够尊重得同时，也让他对这个功能不再是单纯的知道功能点，而是有了一个新的认知（即使这个认知不那么正确）

##### 这里还可以解释一下为什么必须一次验证发一次验证码：

如果一次验证过后可以无次数限制获取验证码，即使每次获取需要等待60s，如果有心人刻意用脚本不断在网页上模拟鼠标点击事件，那一天下来，可是一笔不晓得开支呀。要知道一条短信的费用高达6分钱。

#### 3.2换位思考之自问自答法

##### 是一种穿越时空限制的沟通方法。

###### 在项目开发时，我时常会问自己，如果我是别人，我会如何理解我本人留下来的代码。并不断对已有代码进行提问，为什么要这么写呢？为什么要设置这个参数呢？当时的业务场景又是为什么呢？为什么........

下面同样是在写验证流程路由时记录的代码片段：

![image-20220701201642980](https://github.com/yinhongGITHUB/AdvancedProjectCommunication/blob/main/images/image-20220701201642980.png)可以清楚的看到在该路由文件的开头，详细的标注出了当时开发**验证流程**时的一些注意事项和心得感悟，并在每一流程的上方，都有jsDoc注释进行解释，方便开发者们理解其意图。以便能更加舒服的迭代我的代码。毕竟我可不希望在未来某一天敲代码时突然打喷嚏。被人从背后戳脊梁骨的感觉可太不好受了。

还记得在给我导师分享这个文件的时候，恰巧他问的问题我都已经在上面标注出来了。看着对方的神情从疑惑到更加**疑惑**属实是一件非常振奋人心的事情，哈哈哈哈哈，仿佛穿越时空一般，来到他身边讲解我当时遇到的问题，以及我是如何解决的。

##### 另外，值得注意的是：换位思考的困难的，世界上没有百分百的感同身受，我们只能无限去靠近那个目标，但哪怕是提升百分之一，对整个团队来说都是一件幸福的事。

#### 3.3面对面沟通法

##### 世界上最棒的沟通方法

这是最棒的方法，毕竟，文字是冰冷的，语言却是有温度的。

### 总结：

##### 1.偷梁换柱之偷换概念法：适用于和非技术人员沟通。

##### 2.换位思考之自问自答法：适用于和技术人员沟通，当然，有时对非技术人员用会有奇效。

##### 3.面对面沟通法：适用于一切项目研发场合。

##### 最后，愿我们都有一个良好的工作氛围并为之努力。