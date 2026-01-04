### 基于SpringBoot + Vue的城市社区食堂管理系统.

社区食堂运营系统、智慧社区餐饮平台、社区老年助餐系统、社区中央厨房管理系统

#### 管理员功能模块介绍：
> 用户收货地址：查看和管理所有用户的配送地址信息。公告管理：发布社区食堂相关通知、活动或政策公告。餐品管理：审核、上下架各商家提供的菜品及详情信息。餐品类型：维护菜品类别，如主食、汤品、儿童餐等。订单评价：查看并监管用户对餐品和服务的评价内容。积分兑换：配置可兑换商品或优惠，并审核兑换记录。物品积分：设定不同商品或行为对应的积分奖励规则。会员积分：管理用户积分账户，支持增减与查询操作。商家管理：审核入驻食堂商家资质，管理其营业状态。商家会员：查看商家关联的会员体系及权益设置。订单管理：监控全平台订餐订单状态与履约情况。员工管理：管理平台运营及审核人员的账号与权限。用户管理：维护社区用户资料，处理异常或违规账号。帖子审核：审核用户在社区论坛发布的帖子内容。数据统计：分析订单量、热门餐品、用户活跃等运营数据。

#### 商家功能模块介绍：
> 数据统计：查看本店订单量、销售额、用户评价等经营数据。餐品管理：添加、编辑或下架本店提供的餐品及价格信息。订单评价：查看顾客对本店餐品的评分与文字反馈。订单管理：处理用户下单、备餐、配送及退款等全流程。员工管理：管理本店厨房、配送等岗位员工账号信息。商家会员：设置会员等级、折扣或专属福利策略。商家信息管理：维护店铺名称、简介、营业时间等基本信息。

#### 用户功能模块介绍：
> 用户注册：通过手机号或账号完成平台注册流程。个人信息修改：更新昵称、联系方式、头像等个人资料。收货地址：添加、编辑或选择送餐到家的配送地址。订单下单：浏览餐品、加入购物车并提交订餐请求。订单评价：对已完成的订单进行打分和文字点评。商品收藏：收藏喜爱的餐品，便于下次快速下单。帖子发布与评论：在社区论坛分享用餐体验或互动交流。论坛发帖：创建新话题，参与社区饮食健康等讨论。支付为支付宝沙盒支付：使用支付宝沙箱环境完成模拟支付测试。

#### 安装环境

JAVA 环境 

Node.js环境 [https://nodejs.org/en/] 选择14.17

Yarn 打开cmd， 输入npm install -g yarn !!!必须安装完毕nodejs

Mysql 数据库 [https://blog.csdn.net/qq_40303031/article/details/88935262] 一定要把账户和密码记住

redis

Idea 编译器 [https://blog.csdn.net/weixin_44505194/article/details/104452880]

WebStorm OR VScode 编译器 [https://www.jianshu.com/p/d63b5bae9dff]

#### 采用技术及功能

后端：SpringBoot、MybatisPlus、MySQL、Redis、
前端：Vue、Apex、Antd、Axios

平台前端：vue(框架) + vuex(全局缓存) + rue-router(路由) + axios(请求插件) + apex(图表)  + antd-ui(ui组件)

平台后台：springboot(框架) + redis(缓存中间件) + shiro(权限中间件) + mybatisplus(orm) + restful风格接口 + mysql(数据库)

开发环境：windows10 or windows7 ， vscode or webstorm ， idea + lambok

##### 管理员： 
用户收货地址，公告管理，餐品管理，餐品类型，订单评价，积分兑换，物品积分，会员积分，商家管理，商家会员，订单管理，员工管理，用户管理，帖子审核，数据统计

##### 商家： 
数据统计，餐品管理，订单评价，订单管理，员工管理，商家会员，商家信息管理

##### 用户：
用户注册，个人信息修改，收货地址，订单下单，订单评价，商品收藏，帖子发布与评论，论坛发帖，支付为支付宝沙盒支付


#### 前台启动方式
安装所需文件 yarn install 
运行 yarn run dev

#### 默认后台账户密码
[管理员]
admin
1234qwer

[商家管理员]
shangjia
1234qwer

[用户]
fank
1234qwer

#### 项目截图

|  |  |
|---------------------|---------------------|
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733313905399.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314587984.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314887262.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314563947.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314869376.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314542997.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314846565.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314510235.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314831127.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314226601.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314797431.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314146503.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314769951.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314127351.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314734505.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314076924.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314712174.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314021800.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314671518.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314007255.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314630784.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733313986256.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733314604374.png) | ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/1733313964550.png) |
| ![](https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/work/936e9baf53eb9a217af4f89c616dc19.png) |


#### 演示视频

暂无

#### 获取方式

Email: fan1ke2ke@gmail.com

WeChat: `Storm_Berserker`

`附带部署与讲解服务，因为要恰饭资源非免费，伸手党勿扰，谢谢理解😭`

> 1.项目纯原创，不做二手贩子 2.一次购买终身有效 3.项目讲解持续到答辩结束 4.非常负责的答辩指导 5.**黑奴价格**

> 项目部署调试不好包退！功能逻辑没讲明白包退！

#### 其它资源

[2025年-答辩顺利通过-客户评价🍜](https://berserker287.github.io/2025/06/18/2025%E5%B9%B4%E7%AD%94%E8%BE%A9%E9%A1%BA%E5%88%A9%E9%80%9A%E8%BF%87/)

[2024年-答辩顺利通过-客户评价👻](https://berserker287.github.io/2024/06/06/2024%E5%B9%B4%E7%AD%94%E8%BE%A9%E9%A1%BA%E5%88%A9%E9%80%9A%E8%BF%87/)

[2023年-答辩顺利通过-客户评价🐢](https://berserker287.github.io/2023/06/14/2023%E5%B9%B4%E7%AD%94%E8%BE%A9%E9%A1%BA%E5%88%A9%E9%80%9A%E8%BF%87/)

[2022年-答辩通过率100%-客户评价🐣](https://berserker287.github.io/2022/05/25/%E9%A1%B9%E7%9B%AE%E4%BA%A4%E6%98%93%E8%AE%B0%E5%BD%95/)

[毕业答辩导师提问的高频问题](https://berserker287.github.io/2023/06/13/%E6%AF%95%E4%B8%9A%E7%AD%94%E8%BE%A9%E5%AF%BC%E5%B8%88%E6%8F%90%E9%97%AE%E7%9A%84%E9%AB%98%E9%A2%91%E9%97%AE%E9%A2%98/)

[50个高频答辩问题-技术篇](https://berserker287.github.io/2023/06/13/50%E4%B8%AA%E9%AB%98%E9%A2%91%E7%AD%94%E8%BE%A9%E9%97%AE%E9%A2%98-%E6%8A%80%E6%9C%AF%E7%AF%87/)

[计算机毕设答辩时都会问到哪些问题？](https://www.zhihu.com/question/31020988)

[计算机专业毕业答辩小tips](https://zhuanlan.zhihu.com/p/145911029)

#### 接JAVAWEB毕设，纯原创，价格公道，诚信第一

`网站建设、小程序、H5、APP、各种系统 选题+开题报告+任务书+程序定制+安装调试+项目讲解+论文+答辩PPT`

More info: [悲伤的橘子树](https://berserker287.github.io/)

<p><img align="center" src="https://fank-bucket-oss.oss-cn-beijing.aliyuncs.com/img/%E5%90%88%E4%BD%9C%E7%89%A9%E6%96%99%E6%A0%B7%E5%BC%8F%20(3).png" alt="fankekeke" /></p>
