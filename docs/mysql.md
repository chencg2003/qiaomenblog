> 还未发车，敬请期待
TODO
item2




145138294806373
iOS.33b8fcf640e130323f9a0d442242a98f


邀请流程 == dtapp
Boss管理系统 == dttop
兑换码 == 

useradd
userpwd
zcat grep
vim :%s/a/b/g
set nu

chown
idea使用 : 
    web项目，使用外部 Tomcat 部署
    远程调试

"http://204.236.133.228:8080/dtpay/admin/tool/deliver/compensate?"
          + "sign=miles&isAdmin=miles&id=" + orderId + "&reason=PayPal, by " + who;

需要修改的地方：
阿里支付
AlipayTopupQuota#42

defaultConfFile = "/mnt/sdf/dingtone/billing.properties";


saveInviteInfo\&.*dingtonenP7zcs


saveInviteInfo\&.*dingtonenP7zcs
GetInviter\&.*145138298577413


grep saveInviteInfo homepage.log | grep dingtonenP7zcs


clientKey:
07:07:13,528:  687ba72234f275ab873acda524ad6313
07:07:19,007:  8569467ff26734b2f3262d932ea07ca5
07:07:58,926:  8569467ff26734b2f3262d932ea07ca5
07:09:17,078:  8569467ff26734b2f3262d932ea07ca5
07:13:00,186:  7e62636c2b45bd836515c630a358eb35

1.支付黑名单的清理工具：同一个支付账号，多次支付后会进行购买的限制，导致测试人员无法进行购买测试。
        说明：经过对源码的查看，认为这个功能需要在 billing 项目中，对支付通知流程中的次数限制校验进行功能增强，增加白名单的功能，把测试账号放入白名单。每一个支付方式都是单独的代码进行次数限制，都需要做白名单功能，目前还需要统计总共有哪些需要修改的支付，以及考虑具体的实现方案

邀请设备记录的清理工具：清理设备的被邀请记录，然后测试人员可以继续邀请该设备。
        说明：这个功能原本已经在Boss系统上，但是测试反馈清理的不彻底，即清理后进行邀请还是会邀请失败。经过对邀请流程的梳理，认为原来的删除是彻底的，邀请不成功的可能原因是：邀请流程原本就存在一定的失败概率引起的。所以这个问题，还需要测试人员进一步验证一下清理后邀请不成功是否必现，如果有成功的案例，则说明是邀请流程设计上的问题，并非是删除不彻底的问题。如果全部不成功，则要根据提示信息、日志信息等，再查找和定位问题的具体原因，下周继续跟进

今日小目标：
1. 支付黑名单，看各种源码，整理清楚具体业务，具体修改哪些内容，要怎么修改等等。
        2020年08月31日14:07:42 已经确定了修改的位置，现在要考虑实现方案
2. 继续跟进邀请，具体看时间

3. 三级缓存理解
4. docsify 发布到线上
// 这个博客还是有价值的，研究一下这个话题
https://www.cnblogs.com/grey-wolf/p/13034371.html // 疑问，会不会是要生成不同的 aop 代理的情况？？？但是名称是一样的，也会覆盖earlysingleobjects 中的对象


https://www.cnblogs.com/semi-sub/p/13548479.html
https://mp.weixin.qq.com/s?__biz=MzUxODkzNTQ3Nw==&mid=2247483837&idx=1&sn=e5cefc6653a94995f4bc1424ab1087ce&chksm=f9800767cef78e714e974b4fd059915e0bb7962a2a28a9cd657494d9c73fa5a8288a31831973&mpshare=1&scene=1&srcid=0808o8EdBwabTD193He9eqBq&sharer_sharetime=1596852575289&sharer_shareid=c1c703abc4780acf345dd7a9c02abfe9&exportkey=AcAOjzXMJru9PXWphPLXbU4=&pass_ticket=7XuZHLbnP0t7EwOlXncuJtbFfisCYkUL0hQfPo9rkZzxYe3cqrcr03QTshmFO5ib&wx_header=0#rd

一个对象，多个代理类？？？

为什么一开始要存工厂呢？为什么一开始不直接存三级缓存？这里稍微有点复杂，如果直接存到三级缓存，只能存一个对象，假设以前存这个对象的时候这对象的状态为xa，但是我们这里y要注入的x为xc状态，那么则无法满足；但是如果存一个工厂，工厂根据情况产生任意xa或者xb或者xc等等情况；比如说aop的情况下x注入y，y也注入x；而y中注入的x需要加代理（aop），

 但是加代理的逻辑在注入属性之后，也就是x的生命周期到注入属性的时候x还不是一个代理对象，
 
 那么这个时候把x存起来，然后注入y，获取、创建y，y注入x，获取x；拿出来的x是一个没有代理的对象；
 
 但是如果存的是个工厂就不一样；首先把一个能产生x的工厂存起来，然后注入y，注入y的时候获取、创建y，y注入x，获取x，先从三级缓存获取，为null，然后从二级缓存拿到一个工厂，调用工厂的getObject()；spring在getObject方法中判断这个时候x被aop配置了故而需要返回一个代理的x出来注入给y。当然有的读者会问你不是前面说过getObject会返回一个当前状态的xbean嘛？我说这个的前提是不去计较getObject的具体源码，因为这块东西比较复杂，需要去了解spring的后置处理器功能，这里先不讨论，总之getObject会根据情况返回一个x，但是这个x是什么状态，spring会自己根据情况返回；















#brainTree_quotaForOneCard
brainTree_quotaForOneCard.isOpen=true
brainTree_quotaForOneCard.isOnlyTrace=false
brainTree_quotaForOneCard.amountOfOneWeek=5000
brainTree_quotaForOneCard.timesOfHalfMonth=0
brainTree_quotaForOneCard.timesOfOneMonth=0
brainTree_quotaForOneCard.userCountOf6Month=2
brainTree_quotaForOneCard.userCountOfALL=3
#brainTree_quotaForOneCard_tran
brainTree_quotaForOneCard_tran.isOpen=true
brainTree_quotaForOneCard_tran.isOnlyTrace=false
brainTree_quotaForOneCard_tran.amountOfOneWeek=4000
brainTree_quotaForOneCard_tran.timesOfHalfMonth=0
brainTree_quotaForOneCard_tran.timesOfOneMonth=0
brainTree_quotaForOneCard_tran.userCountOf6Month=2
brainTree_quotaForOneCard_tran.userCountOfALL=3
#paypal_quotaForOneCard
paypal_quotaForOneCard.isOpen=true
paypal_quotaForOneCard.isOnlyTrace=false
paypal_quotaForOneCard.amountOfOneWeek=5000
paypal_quotaForOneCard.timesOfHalfMonth=0
paypal_quotaForOneCard.timesOfOneMonth=0
paypal_quotaForOneCard.userCountOf6Month=3
paypal_quotaForOneCard.userCountOfALL=5
#alipay_quotaForOneAccount
alipay_quotaForOneAccount.isOpen=true
alipay_quotaForOneAccount.isOnlyTrace=false
alipay_quotaForOneAccount.userCountOf12Month=0
alipay_quotaForOneAccount.userCountOfALL=0