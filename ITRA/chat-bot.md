 

#  小诺机器人管理平台运维说明书.v2.0



  

|      |                                                              |
| ---- | ------------------------------------------------------------ |
|      | ![文本框: 小诺机器人 管理平台 运维说明 ](../img/chat-bot/clip_image001.png) |





 

 

使用对象

诺和诺德IT

 

准备方

微软（中国）有限公司

 

日期： 2020年01月07日

版本：2.0

 


 

目录

[1.      仪表盘（Dashboard）... 1](#_Toc29893924)

[2.      自然语言（LUIS）... 1](#_Toc29893925)

[3.      会话（Conversations）... 3](#_Toc29893926)

[3.1.        收集数据（Collect Data）... 13](#_Toc29893927)

[3.2.        对象的属性与方法... 16](#_Toc29893928)

[3.3.        运算符... 21](#_Toc29893929)

[3.4.        代码模板... 21](#_Toc29893930)

[3.5.        Multiple Text Messages. 22](#_Toc29893931)

[3.6.        Make Choice. 24](#_Toc29893932)

[3.7.        Article. 27](#_Toc29893933)

[3.8.        HTTP. 27](#_Toc29893934)

[3.9.        E-mail 30](#_Toc29893935)

[3.10.      Counter. 31](#_Toc29893936)

[3.11.      Emoji 31](#_Toc29893937)

[4.      表情（Emoji）... 36](#_Toc29893938)

[5.      用户（Users）... 37](#_Toc29893939)

[6.      用户组（User Groups）... 42](#_Toc29893940)

[7.      系统设置（System Settings）... 44](#_Toc29893941)

[7.1.        基本设置（Basic）... 44](#_Toc29893942)

[7.2.        仪表盘设置（Dashboard）... 46](#_Toc29893943)

[7.3.        语言理解设置（Language Understanding）... 49](#_Toc29893944)

[7.4.        存储账号设置（Storage Account）... 55](#_Toc29893945)

[7.5.        机器人设置（Bot）... 55](#_Toc29893946)

[7.6.        语音（Speech）... 57](#_Toc29893947)

[7.7.        企业微信设置（Enterprise WeChat）... 58](#_Toc29893948)

[7.8.        微信服务号设置（Enterprise WeChat）... 59](#_Toc29893949)

[8.      计划... 59](#_Toc29893950)

[9.      会话日志... 60](#_Toc29893951)

[10.        用户反馈... 62](#_Toc29893952)

[11.        系统操作日志... 63](#_Toc29893953)

[12.        附加... 64](#_Toc29893954)

[12.1.      如何获取微信用户发送的表情... 64](#_Toc29893955)

 

 


 

本说明及其任何附表、附录、时间表和附件说明如何管理运维[小诺机器人]企业微信相关的智能对话平台, 即[<https://bot-portal-staging.chinacloudsites.cn/admin>].

# 1. 仪表盘（Dashboard）

当登录系统后，默认会进入该页面。如果不是进入该页面的话，可以通过点击左边菜单栏上的Dashboard菜单项，点击后就会打开如下图1.1所示：

![img](../img/chat-bot/clip_image003.jpg)

图1.1

# 2. 自然语言（LUIS） 

通过左边菜单栏点击Chatbot -> LUIS菜单即可进入如下图2.1所示的页面：

![img](../img/chat-bot/clip_image005.jpg)

图2.1

为了加载出LUIS应用列表，请先参考[5.3语言理解设置](#_语言理解设置（Language_Understanding）)一节。

如果想删除LUIS应用，可通过点击图2.1红色框中的红色X按钮。当点击了红色的删除按钮，会显示如下图2.2所示的对话框：

![img](../img/chat-bot/clip_image007.jpg)

图2.2

点击Yes按钮就会删除LUIS应用了，点击No按钮则不会删除掉LUIS应用。

如果想修改应用的名称和描述，可点击图2.1红色框的蓝色铅笔按钮。会显示如下图2.3所示的对话框：

![img](../img/chat-bot/clip_image009.jpg)

图2.3

填写想要的名称和描述，点击Save按钮即可完成修改。如果想保留原来的内容，可点击Cancel按钮取消。

如果想修改LUIS应用的语料，实体等，可点击列表中应用的名称（蓝色字体颜色），将会弹出一个新的页面，该页面的链接地址是在完成[5.3语言理解设置](#_语言理解设置（Language_Understanding）)一节中所设置的LUIS App Portal的值。

修改LUIS应用的语料，实体等，请参考微软官方文档<https://docs.microsoft.com/zh-cn/azure/cognitive-services/luis/>

# 3. 会话（Conversations）

通过点击Chatbot -> Conversations菜单进入如下图3.1所示的会话页面：

![img](../img/chat-bot/clip_image011.jpg)

图3.1

图3.1左边栏展示了可配置的会话列表。如需导入或导出会话配置数据，可点击图3.1右上角的“Import”和“Export”按钮。

如果想要测试Bot，可点击图3.1右上角的“Test”按钮。这里需要注意的是，如果只是想把修改的数据做一次测试而不发布到正式环境中，对修改后的数据，点击图3.1右上角的“Save”按钮即可。

点击“Test”按钮后，会弹出如图3.2所示的界面：

![img](../img/chat-bot/clip_image013.jpg)

图3.2

如果测试结果没有问题，可通过点击图3.2右上角的“Sync”按钮发布到正式环境中。

为了修改会话行为，点击图3.2左边栏的Conversations面板上的项，这里点击“Feedback”项，会展示如图3.3的效果：

![img](../img/chat-bot/clip_image015.jpg)

图3.3

图3.3的Chat面板中，会有一条横虚线，这条线表示会话步骤的分割线。什么是会话步骤？下面我们使用如图3.4所示的预订会议会话作演示：

![img](../img/chat-bot/clip_image017.jpg)

图3.4

如果用户想预订会议，可能会有如下对话（会话1）顺序：

用户：预订会议

机器人：您的会议名称是什么呢？（步骤1）

用户：测试会议

机器人：请输入会议开始时间，例如：“明天上午10点”或“11月23日下午3点”（步骤2）

用户：明天上午10点

机器人：请输入您的会议时长，请以15分钟为单位，例如：“1小时45分钟”（步骤3）

用户：1小时

到这里，机器人接收人需要的信息，请求接口预订会议，并将预订结果回复给用户。（步骤4）

注：如果需要机器人询问用户并等待用户回复问题，则在创建机器人询问的行为后，需要新建步骤。

当用户说了预订会议后，会立即触发“D应用系统_Bizconf_预订“的会话，此时需要配置机器人询问用户的会议名称行为。点击图3.5所示的添加行为按钮：

![img](../img/chat-bot/clip_image019.jpg)

图3.5

弹出如图3.6的行为工具箱：

![img](../img/chat-bot/clip_image021.jpg)

图3.6

注：图3.6中“Go to Other Conversation”，“Ask a Question”和“Make Choice”三个行为会在执行后结束当前步骤，并进入下一步骤。在跳其他会话或者等待用户回复的对话会结束行为所在的步骤。

为了让机器人询问用户“您的会议名称是什么呢？”，点击图3.6中的“Ask a Question”行为，会弹出如图3.7所示弹窗：

![img](../img/chat-bot/clip_image023.jpg)

图3.7

Condition用于配置触发该行为的条件，后面会详细列出If条件有哪些可用配置。这里用户一说“预订会议”，机器人立马触发并询问用户会议的名称，所以这里条件设置为Always。

点击Action选项卡，这里将配置机器人向用户展示的话语，如“您的会议名称是什么呢？”，如下图3.8所示：

![img](../img/chat-bot/clip_image025.jpg)

图3.8

有时需要使会话正确进行，需要强制用户回答问题，那就需要对用户的回复内容进行验证。这里点击Validators选项卡，我们需要判断用户的文本消息是否为空，不为空则验证通过，否则不通过（注：不添加任何验证条件，则不会对用户的消息进行验证）。

在该选项卡中添加一条件，结果如图3.9所示：

![img](../img/chat-bot/clip_image027.jpg)

图3.9

注：用户消息可能是文本消息，也有可能是附件。判断文本消息不为空可配置条件Message.IsNotEmpty，而判断用户是否发送了附件，可配置Message.WithAttachments。

配置好验证条件后，需要确保接下来的步骤的条件与该行为结果匹配，需要配置如图3.10所示的会话数据（ConversationData）的标识：

![img](../img/chat-bot/clip_image029.jpg)

图3.10

注：为何需要配置related key？因为同个步骤中，可能存在两个行为（比如行为1，选项1和2，行为2，选项1和2），都是作选项，在接下来的步骤中，条件的判断如果单独判断数字1，那行为1和行为2的结果都会触发该条件，所以需要使用related key保存到ConversationData中，作为条件判断，判断用户触发的是哪个行为。

点击OK保存。由于需要等待用户回答问题，所以在执行了该行为后，会结束当前会话。因此我们需要新建一个步骤，用于接收用户回复的内容，点击横虚线下的加号按钮，添加新步骤。在新步骤中，我们需要收集上面用户回答的内容，所以勾选右边用户头像旁边的Collect复选，如图3.11所示：

![img](../img/chat-bot/clip_image031.jpg)

图3.10

注：收集用户回复的内容或者关键词，为了在后面的步骤或结果中作为参数使用。

点击Collect复选框旁边的编辑按钮，弹出收集用户消息对话框，如图3.11所示：

![img](../img/chat-bot/clip_image033.jpg)

图3.11

这里需要收集的是用户回答会议名称的内容，所以使用设置message key，为了能在后面更好的使用和明白意思，取个有意义的key是有必要的。（注：后面会对该窗口收集的信息作介绍）

如图3.11，设置了message key的值为meeting name。接下来设置询问用户的会话开始时间，点击机器人头像附近的加号按钮，在弹出的行为工具箱中继续选择“Ask a question”，设置的各选项卡内容如下图3.12-3.14所示：

![img](../img/chat-bot/clip_image035.jpg)

图3.12

![img](../img/chat-bot/clip_image037.jpg)

图3.13

![img](../img/chat-bot/clip_image039.jpg)

图3.14

图3.12中，判断了收集的用户内容中是否包含了会议开始时间。先看下这里的场景，可能用户说“预订明天上午10点的一小时会议”这里提取到的Entity有两个时间，一个是明天上午10点和1小时。此时在第一步时已经设置了Collect需要收集的数据，那在接下来的步骤中，则无需要再询问用户的会话开始时间和时长。如图3.15-3.16展示了步骤一设置的结果：

![img](../img/chat-bot/clip_image041.jpg)

图3.15

![img](../img/chat-bot/clip_image043.jpg)

图3.16

以上为会话配置的内容，接下来将对Collect Data的配置进行说明：

## 3.1.          收集数据（Collect Data）

上图3.16展示的为收集用户消息对话框。如果想收集用户的文本消息或附件，则在Enter message key文本框中设置相关的键，如果值为空则表示不收集该内容；

如果想收集LUIS识别的用户意图，则设置Enter intent key值。用户意图可通过LUIS管理界面中查看，如图3.1.1所示：

![img](../img/chat-bot/clip_image045.jpg)

图3.1.1

如果想根据实体的名称收集实体值，添加Entity name and key collection项。实体名称可通过LUIS管理界面中查看，如图3.1.2所示：

![img](../img/chat-bot/clip_image047.jpg)

图3.1.2

有的实体值可点击实体名称查看。而其他实体值，像datetimeV2和number这种，可进入到如下图3.1.3所示：

![img](../img/chat-bot/clip_image049.jpg)

图3.1.3

点击图3.1.3中的链接，弹出的新窗口中，修改链接地址的查询参数q，如设置“明天上午10点的一小时会议”，会显示如下图3.1.4所示的Json数据：

![img](../img/chat-bot/clip_image051.jpg)

图3.1.4

注：图中的谷歌浏览器装了JSON数据查看插件。

如果想根据实体类型收集实体值，添加Entity type and key collection(Resolution)项。图3.1.4中展示了实体类型builtIn.datetimeV2.datetime的resolution的值value为2020-01-07 10:00:00。

## 3.2.          对象的属性与方法

注：字符及字符串需要使用双引号。

支持的对象属性与方法如下表3.2.1所示：

| 对象             | 说明                                                         | 示例                                                         |
| ---------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Channel          | 频道，可用于判断是否是MSTeams，企业微信和微信公众号。   Channel的属性见表3.2.2 | Channel.IsMSTeams   Channel.IsWeChat   Channel.IsEnterpriseWeChat |
| ConversationData | 会话数据，获取用户的消息，意图，实体或Related   Key。   属性和方法见表3.2.3 | ConversationData.Contains(“meeting name”)   ConversationData.Get(“meeting   name”) |
| DateTime         | 获取当前系统时间。   属性见表3.2.4                           | DateTime.Local.Now.Year   DateTime.UTC.Now.Year              |
| LUIS             | LUIS自然语言理解。   LUIS目前仅有Entities属性，见表3.2.6查询Entities的属性和方法 | LUIS.Entities.Contains(“number”)                             |
| Message          | 用于判断用户消息是否为空。   属性见表3.2.7                   | Message.IsNotEmpty   Message.WithAttachments                 |
| Parse            | 数据转换。   方法见表3.2.8                                   | Parse.ToJson(jsonString)   注：jsonString对象或变量必须是字符串 |
| Random           | 生成随机数   属性和方法见表3.2.10                            | Random.Number(1,   10)   Random.Current                      |
| User             | 获取当前访问的用户信息   属性见表3.2.11                      | User.Id   User.Name                                          |
| Counter          | 获取用户当前的计数值                                         | Counter.Count                                                |
| BizVideo         | Biz接口参数生成与加密   属性和方法见表3.2.12                 | BizVideo.BuildTimeStamp()                                    |

表3.2.1

| 对象               | Channel    |                            |
| ------------------ | ---------- | -------------------------- |
| 属性/方法          | 说明       | 示例                       |
| IsMSTeams          | MS Teams   | Channel.IsMSTeams          |
| IsWeChat           | 微信公众号 | Channel.IsWeChat           |
| IsEnterpriseWeChat | 企业微信   | Channel.IsEnterpriseWeChat |

表3.2.2

| 对象      | ConversationData                   |                                           |
| --------- | ---------------------------------- | ----------------------------------------- |
| 属性/方法 | 说明                               | 示例                                      |
| Contains  | 用于判断会话数据中是否包含指定key  | ConversationData.Contains(“meeting name”) |
| Get       | 通过指定键从会话数据中获取存储的值 | ConversationData.Get(“meeting   name”)    |

表3.2.3

注：从ConversationData获取用户的文本消息，需要使用ConversationData.Get(“meeting name”).Text

| 对象      | DateTime                                        |                          |
| --------- | ----------------------------------------------- | ------------------------ |
| 属性/方法 | 说明                                            | 示例                     |
| Local     | 获取系统当前时间                                | DateTime.Local.Now.Month |
| UTC       | 获取系统当前的UTC时间                           | DateTime.UTC.Now.Month   |
| 说明      | Local和UTC都只有属性Now，属性Now的属性见表3.2.5 |                          |

表3.2.4

| 对象      | Now                                                   |                                                           |
| --------- | ----------------------------------------------------- | --------------------------------------------------------- |
| 属性/方法 | 说明                                                  | 示例                                                      |
| Year      | 获取当前时间的年份                                    | DateTime.Local.Now.Year   DateTime.UTC.Now.Year           |
| Month     | 获取当前时间的月份                                    | DateTime.Local.Now.Month   DateTime.UTC.Now.Month         |
| Day       | 获取当前时间月份的第几号                              | DateTime.Local.Now.Day   DateTime.UTC.Now.Day             |
| Hour      | 获取当前时间的小时                                    | DateTime.Local.Now.Hour   DateTime.UTC.Now.Hour           |
| Minute    | 获取当前时间的分钟                                    | DateTime.Local.Now.Minute   DateTime.UTC.Now.Minute       |
| Second    | 获取当前时间的秒                                      | DateTime.Local.Now.Second   DateTime.UTC.Now.Second       |
| DayOfWeek | 获取当前时间的星期几   星期日为0，星期一为1，以此类推 | DateTime.Local.Now.DayOfWeek   DateTime.UTC.Now.DayOfWeek |

表3.2.5

| 对象         | Entities                   |                                                           |
| ------------ | -------------------------- | --------------------------------------------------------- |
| 属性/方法    | 说明                       | 示例                                                      |
| Contains     | 判断是否存在指定名称的实体 | LUIS.Entities.Contains(“number”)                          |
| Get          | 获取指定名称的实体值       | LUIS.Entities.Get(“number”)                               |
| ContainsType | 判断是否存在指定类型的实例 | LUIS.Entities.ContainsType(“builtIn.datetimeV2.datetime”) |
| GetByType    | 通过指定实体类型获取实体值 | LUIS.Entities.GetByType(“builtIn.datetimeV2.datetime”)    |

表3.2.6

| 对象            | Message                        |                         |
| --------------- | ------------------------------ | ----------------------- |
| 属性/方法       | 说明                           | 示例                    |
| IsNotEmpty      | 判断用户发送的文本消息是否为空 | Message.IsNotEmpty      |
| WithAttachments | 判断用户是否发送了附件         | Message.WithAttachments |

表3.2.7

| 对象          | Parse                                      |                                                              |
| ------------- | ------------------------------------------ | ------------------------------------------------------------ |
| 属性/方法     | 说明                                       | 示例                                                         |
| ToJson        | Json字符串转Json对象                       | Parse.ToJson(jsonString)   注：如果json的键值是常量，为了能进行条件判断，请先用Parse.ToStringValue(Parse.ToJson(jsonString).count) == “1” |
| ToInt         | 字符串转换成整形数                         | Parse.ToInt(“1”)                                             |
| ToLong        | 字符串转换成长整形数                       | Parse.ToLong(“1”)                                            |
| ToDouble      | 字符串转型成双精度数                       | Parse.ToDouble(“1.1”)                                        |
| ToBoolean     | 字符串转成成布尔值                         | Parse.ToBoolean(“true”)                                      |
| ToStringValue | 对象转换成字符串                           | Parse.ToStringValue(1)                                       |
| ToDateTime    | 字符串转成日期   转换后的日期对象见表3.2.9 | Parse.ToDateTime(“2020-1-7   13:56”)                         |

表3.2.8

| 对象           | Parse.ToDateTime(“2020-1-7   13:56”)返回的对象        |                                                              |
| -------------- | ----------------------------------------------------- | ------------------------------------------------------------ |
| 属性/方法      | 说明                                                  | 示例                                                         |
| Year           | 获取当前时间的年份                                    | Parse.ToDateTime(“2020-1-7   13:56”).Year                    |
| Month          | 获取当前时间的月份                                    | Parse.ToDateTime(“2020-1-7   13:56”).Month                   |
| Day            | 获取当前时间月份的第几号                              | Parse.ToDateTime(“2020-1-7   13:56”).Day                     |
| Hour           | 获取当前时间的小时                                    | Parse.ToDateTime(“2020-1-7   13:56”).Hour                    |
| Minute         | 获取当前时间的分钟                                    | Parse.ToDateTime(“2020-1-7   13:56”).Minute                  |
| Second         | 获取当前时间的秒                                      | Parse.ToDateTime(“2020-1-7   13:56”).Second                  |
| DayOfWeek      | 获取当前时间的星期几   星期日为0，星期一为1，以此类推 | Parse.ToDateTime(“2020-1-7   13:56”).DayOfWeek               |
| AddYears       | 添加或者减少年份                                      | Parse.ToDateTime(“2020-1-7   13:56”).AddYears(1)             |
| AddMonths      | 添加或者减少月份                                      | Parse.ToDateTime(“2020-1-7   13:56”).AddMonths(1)            |
| AddDays        | 添加或者减少天数                                      | Parse.ToDateTime(“2020-1-7   13:56”).AddDays(1)              |
| AddHours       | 添加或者减少小时数                                    | Parse.ToDateTime(“2020-1-7   13:56”).AddHours(1)             |
| AddMinutes     | 添加或者减少分钟数                                    | Parse.ToDateTime(“2020-1-7   13:56”).AddMinutes(1)           |
| AddSeconds     | 添加或者减少秒数                                      | Parse.ToDateTime(“2020-1-7   13:56”).AddSeconds(1)           |
| ToFormatString | 按指定格式将日期转换成字符串                          | Parse.ToDateTime(“2020-1-7   13:56”).ToFormatString(“YYYY/MM/DD HH:mm:ss”) |

表3.2.9

| 对象      | Random                 |                        |
| --------- | ---------------------- | ---------------------- |
| 属性/方法 | 说明                   | 示例                   |
| Number    | 生成指定范围内的随机数 | Random.Number(1,   10) |
| Current   | 获取当前生成的随机数值 | Random.Current         |

表3.2.10

| 对象      | User       |           |
| --------- | ---------- | --------- |
| 属性/方法 | 说明       | 示例      |
| Id        | 获取用户ID | User.Id   |
| Name      | 获取用户名 | User.Name |

表3.2.11

| 对象             | BizVideo                                                |                                                              |
| ---------------- | ------------------------------------------------------- | ------------------------------------------------------------ |
| 属性/方法        | 说明                                                    | 示例                                                         |
| BuildTimeStamp   | 生成时间戳                                              | BizVideo.BuildTimeStamp()                                    |
| CurrentTimeStamp | 获取当前生成的时间戳                                    | BizVideo.CurrentTimeStamp()                                  |
| MD5Hash          | 生成签名   接收3个字符串参数   userId,   key, timestamp | BizVideo.MD5Hash(User.Id,   “123456789”, BizVideo.BuildTimeStamp()) |

表3.2.12

## 3.3.          运算符

| 逻辑运算符 | 且（&&），或（\|\|）和非（!）                                |
| ---------- | ------------------------------------------------------------ |
| 比较运算符 | 等于（==），不等于（!=或<>），小于（<），小于或等于（<=），大于（>），大于或等于（>=） |
| 算数运算符 | 加（+），减（-），乘（*），除（/），求余（%）                |

表3.3.1

## 3.4.          代码模板

在设置If条件时，无需使用<% %>符号。

而当插件的配置界面有如下图3.4.1所示提示时，则可通过输入模板<% %>符号执行代码运算：

![img](../img/chat-bot/clip_image053.jpg)

图3.4.1

示例如：  

|      |                                                              |
| ---- | ------------------------------------------------------------ |
|      | ![文本框: 诺诺已成功为您预定！ 会议主题：<% Parse.ToJson(ConversationData.Get("reservation result").Content).data.confName %> 会议时间：<% Parse.ToDateTime(Parse.ToStringValue(Parse.ToJson(ConversationData.Get("reservation result").Content).data.startTime)).AddHours(8).ToFormatString("yyyy-MM-dd HH:mm:ss") %> 参会链接：<% Parse.ToJson(ConversationData.Get("reservation result").Content).data.joinUrl %> 会议ID：<% Parse.ToJson(ConversationData.Get("reservation result").Content).data.confNumber %> 电话接入号码：<% Parse.ToJson(ConversationData.Get("reservation result").Content).data.videoPhone %> ](../img/chat-bot/clip_image054.png) |





## 3.5.          Multiple Text Messages

为机器人添加文本消息的响应行为，可以通过Actions Toolbox中选中Multiple Text Messages，如图3.5.1所示。

![img](../img/chat-bot/clip_image056.jpg)

图3.5.1

图3.5.1中展示了Multiple Text Messages组件的配置功能，基本上每个行为组件都有条件（Condition）选项卡。

可点击行为（Action）选择卡配置机器人回复用户的消息。如下图3.5.2所示：

![img](../img/chat-bot/clip_image058.jpg)

图3.5.2

如需要将返回的文本消息转语句，可勾选Is Voice列的复选框。而如果需要随机回复消息，可添加多条文本消息，并勾选Random message即可。

这里需要说明的是，回复用户的文本消息可使用代码动态填充数据。例如用户预订会议室，使用HTTP组件调用接口后，将接口返回的结果填充到回复给用户的消息中。如图3.5.2显示了成功调用BizConf接口后，从接口返回的数据中获取会议主题，会议时间，参会链接等信息。

## 3.6.          Make Choice

如果需要让用户做选择题，可以通过Actions Toolbox中选中Make Choice，如图3.6.1所示：

![img](../img/chat-bot/clip_image060.jpg)

图3.6.1

Make Choice行为有四个选项卡，分别是条件（Condition），行为（Action），验证器（Validators）和关联键（Related Key）。

下面讲解各必要的选项卡。

点击Action选项卡，如下图3.6.2所示：

![img](../img/chat-bot/clip_image062.jpg)

图3.6.2

如图3.6.2所示，这里配置了选择题的题目，选择题的各选项序号和标题。

点击Validators选项卡，这里配置对用户的消息验证，如可能只有3个选项1，2和3，但是用户却选择4，那是否允许让用户选择4，如果不允许，此时验证器就起了作用。验证器的选项卡配置如下图3.6.3所示：

![img](../img/chat-bot/clip_image064.jpg)

图3.6.3

点击Related Key选项卡，这里为什么需要配置该值呢？请看下图3.6.4所示：

![img](../img/chat-bot/clip_image066.jpg)

图3.6.4

这里同个步骤，出现两道选择题，一道是“请问您当前在哪里办公？”，另一道是“请问您使用的是什么操作系统？”，两道选择题都有同样的选项1、2和3。用户可能做了第一道选择题，选择1。然后机器人收到了用户的选项1，需要进行相关的处理，如下图3.6.5所示：

![img](../img/chat-bot/clip_image068.jpg)

图3.6.5

这里有两个条件只要都满足1，都会执行。但是其实这两个满足1的条件都是各自对应图3.6.4中的两道题。那这时设置关联的Related Key就有必要了。

## 3.7.          Article

通过添加Article Message行为，可配置如下图3.7.1所示的参数：

![img](../img/chat-bot/clip_image070.jpg)

图3.7.1

该行为在微信服务号的响应结果如下图3.7.2所示：

![img](../img/chat-bot/clip_image072.jpg)

图3.7.2

## 3.8.          HTTP

通过添加HTTP行为，可打开HTTP的配置界面如下图3.8.1所示：

![img](../img/chat-bot/clip_image074.jpg)

图3.8.1

如图3.8.1，在Basic选择卡中，可以配置HTTP请求的地址，请求的方式和将返回结果保存到会话数据中的Key（注：可通过该Key获取请求结果并做后续处理）。

设置Key后，HTTP请求返回的结果保存到会话数据，需要通过以下两个属性获取值：

| 对象       | HTTP响应结果                  |                                                     |
| ---------- | ----------------------------- | --------------------------------------------------- |
| 属性/方法  | 说明                          | 示例                                                |
| StatusCode | 响应码，如200，404，500等数值 | ConversationData.Get("response  result").StatusCode |
| Content    | 响应内容（字符串）            | ConversationData.Get("response  result").Content    |

打开Query Parameters选择卡，可配置请求的查询参数，如图3.8.2所示：

![img](../img/chat-bot/clip_image076.jpg)

图3.8.2

什么是查询参数？就像打开浏览器，在百度搜索相关信息，会看到浏览器上问号后的键值对，如下图3.8.3所示：

![img](../img/chat-bot/clip_image078.jpg)

图3.8.3

还可设置HTTP的请求头和请求体，详情请百度了解如何用如Postman这些工具进行HTTP请求。

## 3.9.          E-mail

通过添加E-mail行为，可打开如图3.9.1所示配置对话框：

 

![img](../img/chat-bot/clip_image080.jpg)

图3.9.1

这里可配置SMTP邮件服务器的地址，帐号和密码。

点击Mail选择卡，如图3.9.2所示：

![img](../img/chat-bot/clip_image082.jpg)

图3.9.2

这里可配置邮件的发送人邮箱地址，接收人邮箱地址，主题和邮件内容。

如果需要邮件附带附件，可点击Attachments选项卡配置邮件的Key。目前这里的Key仅可配置为通过Collect配置的message key。

比如有种场景，询问用户是否满意当前会话结果，如果用户不满意，可收集用户反馈的内容。用户反馈的内容可以是一些截图或者文件，此时只需要设置Collect的message key收集用户反馈的内容，并将该key作为e-mail行为的attachments key即可。系统会通过该key获取并将用户上传的文件作为附件发送给接收人。

## 3.10.     Counter

通过添加计数器行为，可打开如下图3.10.1所示对话框：

![img](../img/chat-bot/clip_image084.jpg)

图3.10.1

图3.10.1中可配置最大计数值，当达到该值时，会重新计数。需要注意的时，该值是全局值，也就是说，有的地方配置5，有的地方配置3，但只要3先被触发，5就永远不会达到。

有什么使用场景呢？可能用户反馈不满意，不想每次都发送邮件给服务人员，那可以设置同一用户反馈多少次不满意后才发送邮件给服务人员。

## 3.11.     Emoji

添加Emoji行为，可打开如下图3.11.1所示对话框：

![img](../img/chat-bot/clip_image086.jpg)

图3.11.1

发送表情包，可能交互的平台不同，像在微信不支持动态图片，却识别文字，而在MSTeams中微信支持的文字却没有任何作用，此时就需要发送成图片。

为此，点击Condition选项卡，如果需要支持MSTeams并发送图片，输入如下图3.11.2所示的条件：

![img](../img/chat-bot/clip_image088.jpg)

图3.11.2

回到Emoji选项卡，点击编辑按钮（铅笔），会看到在“[第四节表情](#_表情（Emoji）)”一节中添加的表情列表，如下图3.11.3所示：

![img](../img/chat-bot/clip_image090.jpg)

图3.11.3

注：图3.11.3列表中的表情得通过QQ的对话窗口中，将每一个表情保存到电脑上并将后缀png改成gif。而表情对应的文字符，可通过会话日志（Conversation Log）获取（在未有对应表情图片显示的情况下会显示成文字）。

选中表情后，如下图3.11.4所示：

 

![img](../img/chat-bot/clip_image092.jpg)

图3.11.4

点击OK保存即可。

而如果需要判断交互平台是企业服务号，则可修改条件为如下图3.11.5所示：

![img](../img/chat-bot/clip_image094.jpg)

图3.11.5

然后点击Emoji选项卡，并勾选Send emoji label复选框和所需要的文本标签即可，如下图3.11.6所示：

![img](../img/chat-bot/clip_image096.jpg)

图3.11.6

与微信交互后的效果如下图3.11.7所示：

![img](../img/chat-bot/clip_image098.jpg)

图3.11.7

由于可能交互的平台非Teams和微信，所以我们可以修改条件为else和emoji为仅发送图片，在html表现效果如下图3.11.8所示：

![img](../img/chat-bot/clip_image100.jpg)

图3.11.8

# 4. 表情（Emoji）

通过点击Chatbot -> Emoji菜单进入如下图4.1所示的表情管理页面：

![img](../img/chat-bot/clip_image102.jpg)

图4.1

# 5. 用户（Users）

通过点击Security -> Users菜单进入如下图5.1所示的用户管理页面：

![img](../img/chat-bot/clip_image104.jpg)

图5.1

如图5.1所示列表中展示了创建的各个用户账号。在Action列中，如果是系统默认用户，则无法删除。当想要添加新用户，可点击右上角的新增（New）按钮，会进入到如下图5.2所示页面：

![img](../img/chat-bot/clip_image106.jpg)

图5.2

注：目前项目中Channel选项卡没有任何作用。

该系统添加的用户邮箱，由于项目目前使用了Azure Active Directory域作为用户身份验证服务，所以配置的邮箱必须存在于Azure Active Directory域中。

在此处添加完成用户后，打开[https://portal.azure.cn](https://portal.azure.cn/)或<https://ms.portal.azure.com>。登录后，点击下图5.3中的Azure Active Directory菜单：

![img](../img/chat-bot/clip_image108.jpg)

图5.3

在打开的如下图5.4所示页面中，点击主面板左边菜单栏中的Enterprise applications菜单：

 

![img](../img/chat-bot/clip_image110.jpg)

图5.4

然后在下图5.5所示的列表中点击项目关联的应用程序名称：

![img](../img/chat-bot/clip_image112.jpg)

图5.5

会进入到如下图5.6的页面：

![img](../img/chat-bot/clip_image114.jpg)

图5.6

点击左边Users and groups菜单，并点击工具栏上的Add User按钮，如图5.7所示：

![img](../img/chat-bot/clip_image116.jpg)

图5.7

在下图5.8中点击Users项，再在右边的列表中搜索并点击需要的用户：

![img](../img/chat-bot/clip_image118.jpg)

图5.8

选择完成后，点击Select，会显示如下图5.9所示页面效果：

![img](../img/chat-bot/clip_image120.jpg)

图5.9

最后点击图5.9主面板左下角的Assign按钮，稍作等待，会自动跳回到图5.7显示的列表页面。在此页面中即可看到点击的用户。

# 6. 用户组（User Groups）

通过点击Security -> User Groups菜单进入如下图6.1所示的系统整体设置页面：

![img](../img/chat-bot/clip_image122.jpg)

图6.1

注：系统默认角色无法删除。

通过点击New或者添加用户组的名称，会进入到如图6.2界面，可通过该界面修改或新增用户组：

![img](../img/chat-bot/clip_image124.jpg)

图6.2

 

# 7. 系统设置（System Settings）

通过点击System -> System Settings菜单进入如下图7.1所示的系统整体设置页面：

![img](../img/chat-bot/clip_image126.jpg)

图7.1

以下逐一介绍设置界面中的各个子项功能。

## 7.1.          基本设置（Basic）

通过点击Basic面板，可看到如图7.1.1所示页面：

 

![img](../img/chat-bot/clip_image128.jpg)

图7.1.1

### 参数说明

| 名称           | 描述                                                         |
| -------------- | ------------------------------------------------------------ |
| Default Locate | 使用Azure的Speech服务时需要用到。   例如在Speech进行语音文字识别或文字转语音时使用。 |
| Website Host   | 网站的域名。   目前系统在向用户推送反馈表单页面时使用。      |


 

 

## 7.2.          仪表盘设置（Dashboard）

点击Dashboard面板，可看到如图7.2.1所示页面：

![img](../img/chat-bot/clip_image130.jpg)

图7.2.1

### 参数说明

| 名称            | 描述                             |
| --------------- | -------------------------------- |
| Enable Power BI | 是否启用通过iframe嵌入Power BI。 |
| Power BI URL    | 嵌入的Power BI仪表盘页面网址。   |

假设您已经创建好了自己的仪表盘并完成发布，此时需要获取Power BI的网址，可通过以下步骤完成：

\1.     登录[https://msit.powerbi.com](https://msit.powerbi.com/)；

\2.     点击左边栏上您需要使用的Power BI所在的工作区；

\3.     点击报表选项卡并点击您要使用的报表，这里点击dashboard报表，如图7.2.2所示；

![img](../img/chat-bot/clip_image132.jpg)

图7.2.2

\4.     进入报表视图页面后，报表视图页面上会有菜单栏，依次点击“文件”->“发布到Web”，如图7.2.3所示；

![img](../img/chat-bot/clip_image134.jpg)

图5.2.3

\5.     在弹出窗口中，只需要复制“您可以在电子邮件中发送的链接”标题下方的文本框中的内容即可，如图7.2.4所示。

![img](../img/chat-bot/clip_image136.jpg)

图7.2.4


 

 

## 7.3.          语言理解设置（Language Understanding）

点击Language Understanding面板，可看到如图7.3.1所示页面：

![img](../img/chat-bot/clip_image138.jpg)

图7.3.1

### 参数说明

| 名称                            | 描述                                                         |
| ------------------------------- | ------------------------------------------------------------ |
| Authoring Endpoint              | 获取LUIS用户账号下的数据的请求地址。                         |
| Authoring Key                   | 该密钥用于LUIS用户账号下的数据。                             |
| Min Score                       | LUIS识别结果中会返回对用户意图识别的分数。该值为允许通过的最小预测分数值，值范围0到1之间。 |
| LUIS App Portal                 | 该项为管理系统中Chatbot->LUIS所列应用的跳转网址，参数中的{0}为应用ID的点位符。 |
| Threshold Score                 | 临界值。对通过Min Score中识别结果，获取非None的意图。如果所有意图都为None，则返回所有None结果。否则只获取超过了该值的非None结果。 |
| Pure English Words Optimization | 是否启用纯英文优化。如果启用，用户消息如果为纯英文（包括不可见字符），则将最高预测结果0.9及以上分数的None的意图，且第二意图超过Min Score的项，将第二意作为第一意图处理，排除掉None意图。 |

当设置或修改Authoring Endpoint和Authoring Key时，需要等待片刻，系统会自动加载账号下的所有App（如图7.3.1），你可根据需要，勾选需要的App。要注意的是，需要设置好App的终结点（Endpoint）和密钥（Endpoint Key）。如果勾选的App的终结点或者密钥两者缺一，会被Bot在运行过程中忽略掉。

为获取以上配置参数，请先登录<https://luis.azure.cn/>。

### 7.3.1.         获取Authoring Endpoint和Authoring Key

登录Luis管理平台后，点击右上角的用户头像，会显示如图7.3.2所示页面效果：

![img](../img/chat-bot/clip_image140.jpg)

图7.3.2

点击设置按钮后，会显示如图7.3.3所示页面：

![img](../img/chat-bot/clip_image142.jpg)

图7.3.3

在图7.3.3中的创建键即为Authoring Key。而Authoring Endpoint需要创建 “语言理解”服务获取，具体操作步骤如下：

\1.     登录[https://portal.azure.cn](https://portal.azure.cn/)，点击左边栏菜单项“创建资源”，然后搜索“语言理解”，会显示如下图7.3.4所示：

![img](../img/chat-bot/clip_image144.jpg)

图7.3.4

\2.     点击“语言理解”项并点击“创建”按钮，打开如图7.3.5所示页面，并根据需要设置相关参数：

![img](../img/chat-bot/clip_image146.jpg)

图7.3.5

\3.     设置好参数后点击“创建”按钮，需要等待些时间以完成创建。接着打开前面登录的<https://luis.azure.cn/>站点，随意点击一个应用，进入如下图7.3.6所示页面：

![img](../img/chat-bot/clip_image148.jpg)

图7.3.6

\4.     点击“管理”或“MANAGE”选项卡，点击左边栏“Keys and Endpoints”或“密钥和终结点”菜单项，会打开如图7.3.7所示页面：

![img](../img/chat-bot/clip_image150.jpg)

图7.3.7

\5.     点击页面主面板中的“分配资源”或“Assign resource”按钮（如图7.3.7红框），在弹出窗口中选项步骤2和3所创建的“语言理解”服务，并点击“分配资源”或“Assign resource”按钮，如图7.3.8所示：

![img](../img/chat-bot/clip_image152.jpg)

图7.3.8

完成以上步骤后，会看到如下图7.3.9所示页面：

![img](../img/chat-bot/clip_image154.jpg)

图7.3.9

在些页面中的资源列表处，Key1或Key2即为Endpoint Key，而Endpoint和Authoring Endpoint只需要使用其<https://+域名部分即可>。

注：Starter_Key仅供测试用. 实际产品须收费订阅key, 可登录[https://portal.azure.cn](https://portal.azure.cn/)到并创建“语言理解”服务，并回到图7.3.7的界面，点击分配资源按钮，将应用与所创建的“语言理解”服务进行关联，然后使用“语言理解”服务的密钥和终结点即可。


 

 

## 7.4.          存储账号设置（Storage Account）

点击Storage Account面板，可看到如图7.4.1所示页面：

![img](../img/chat-bot/clip_image156.jpg)

图7.4.1

### 参数说明

| 名称                      | 描述                                                         |
| ------------------------- | ------------------------------------------------------------ |
| Store Path of Other Files | 存储Bot的Send Messages模块中文件消息上传的文件或反馈表单中用户上传的文件。 |
| Store Path of Videos      | 存储Bot的Send Messages模块中视频消息上传的视频。             |
| Store Path of Pictures    | 存储Bot的Send Messages模块中图片消息上传的图片。             |
| Store Path of Voices      | 存储Bot以语音消息回应用户所产生的语音文件。                  |

注：四个Store Path所设置的路径，以反斜杆分割，第一部分为存储帐户的容器名称，第二部分起才为容器下的文件夹名称。

## 7.5.          机器人设置（Bot）

点击Bot面板，可看到如图7.5.1所示页面：

![img](../img/chat-bot/clip_image158.jpg)

图7.5.1

### 参数说明

| 名称                                                       | 描述                                                       |
| ---------------------------------------------------------- | ---------------------------------------------------------- |
| Using Capital Letters                                      | 使用大写字母。机器人接收到消息后，会将字母都转换成大写字母 |
| Direct Line Conversation Expires In(Unit:Second)           | 会话过期时间，单位秒                                       |
| After conversation ends, Feedback Expires In(Unit: second) | 会话结束后，发送给用户的反馈，有效时间。单位：秒           |

 


 

 

## 7.6.          语音（Speech）

点击Speech面板，打开如下图7.6.1所示页面：

![img](../img/chat-bot/clip_image160.jpg)

图7.6.1

该面板分为语音转文本（Speech To Text）和文本转语音（Text To Speech）。

### 语音转文本参数说明

| 名称                        | 描述                                   |
| --------------------------- | -------------------------------------- |
| Return User’s Voice Content | 是否返回识别出的文本内容               |
| Removed Punctuation         | 识别出的文本内容需要去掉结尾的标点符号 |
| Subscription Key            | 订阅密钥                               |
| Region                      | 订阅所在区域                           |

### 文本转语音参数说明

| 名称                        | 描述                     |
| --------------------------- | ------------------------ |
| URL of Getting Access Token | 获取Token的链接地址      |
| Subscription Key            | 订阅密钥                 |
| Text to Speech URL          | 文本转语音的处理链接地址 |
| Voice Name                  | 讲语音的人               |
| Output Format               | 输出的语音格式           |
| Content Type                | 语音文件的MIME           |
| File Extension              | 语音保存的文件名后缀     |

 

 

## 7.7.          企业微信设置（Enterprise WeChat）

点击Enterprise WeChat面板，打开如下图7.7.1所示页面：
 ![img](../img/chat-bot/clip_image162.jpg)

图7.7.1

### 参数说明

| 名称                | 描述       |
| ------------------- | ---------- |
| Enterprise ID       | 微信企业ID |
| Application Secret  | 应用密钥   |
| Application AgentId | 应用ID     |

详情请参考企业微信相关文档和应用管理内容。

<https://work.weixin.qq.com/api/doc#90000/90135/90664>

<https://work.weixin.qq.com/?from=openApi>

## 7.8.          微信服务号设置（Enterprise WeChat）

点击WeChat面板，打开如下图7.8.1所示页面：
 ![img](../img/chat-bot/clip_image164.jpg)

图7.8.1

### 参数说明

| 名称                                  | 描述                                       |
| ------------------------------------- | ------------------------------------------ |
| AppID                                 | 应用程序ID                                 |
| AppSecret                             | 应用密钥                                   |
| Token                                 |                                            |
| EncodingAESKey                        |                                            |
| Proactive Message                     | 主动消息（如需配置服务号，请开启，勿关闭） |
| Using WeChat Voice Recognition Result | 是否使用微信的语音识别结果                 |

# 8. 计划

通过点击System -> Schedules菜单进入如下图8.1所示的页面：

![img](../img/chat-bot/clip_image166.jpg)

图8.1

目前项目仅支持手动点击执行计划，此仅存在收集用户反馈的计划。

如需要执行计划，点击图8.1中Action列上的钟表按钮，系统会立即执行该计划。

# 9. 会话日志

通过点击Log -> Conversations菜单进入如下图9.1所示的页面：

![img](../img/chat-bot/clip_image168.jpg)

图9.1

图9.1的Filter面板提供了导出数据到JSON，导出数据到Excel和数据筛选。

通过在各文本框中输入需要的条件，点击Filter按钮，列表中即会根据筛选条件显示筛选后的数据。

在列表的Action列中，点击一项的查看（眼睛）按钮，可看到如下图9.2所示对话框：

![img](../img/chat-bot/clip_image170.jpg)

图9.2

图9.2的对话框中显示了用户与机器人的整个会话过程，同时在用户一栏下还显示了各个LUIS应用识别的意图与分数。

# 10.        用户反馈

通过点击Log -> Feedbacks菜单进入如下图10.1所示的页面：

![img](../img/chat-bot/clip_image172.jpg)

图10.1

在该列表中，可以看到执行了Feedback Collection计划后，收到邀请的用户对在使用聊天机器人过程中所作出的评分与建议。Score显示了用户的评分，目前评分总分为5分。而Suggestion Content列显示了用户的建议。

如果用户未评价，则Suggestion Content会显示Waiting for user’s feedback。

如果用户上传了图片，在鼠标经过的数据行时，会显示如下图10.2所示的提示信息：

![img](../img/chat-bot/clip_image174.jpg)

图10.2

注：截图无法截取到鼠标形状，图10.2所在的行为第8行。

点击数据行，会展开所点击的数据行并显示用户上传的图片。

# 11.        系统操作日志

通过点击Log -> Activities菜单进入如下图11.1所示的页面：

![img](../img/chat-bot/clip_image176.jpg)

图11.1

图11.1中的列表，展示了哪些用户编辑了系统中的数据。

# 12.        附加

## 12.1.     如何获取微信用户发送的表情

![img](../img/chat-bot/clip_image178.jpg)

图12.1.1

打开LUIS，进入其中一个APP，添加一个List类型的实体，如图12.1.1中已经添加的emoji。点击该实体，可看到如下图12.1.2所示界面：

![img](../img/chat-bot/clip_image180.jpg)

图12.1.2

注：Normalized Value的值英文大小写不区分，所以微信的文字表情，最好以企业微信的中文作为主值，将符号作为同义词。

Normailzed Value设置的值会在LUIS识别用户意图时作为实体的值返回。可通过如下图12.1.3所示界面按实体名称收集表情实体：

![img](../img/chat-bot/clip_image182.jpg)

图12.1.3

注：如果用户的语言中存在相同List实体的多个仅，Bot仅取第一个值。

下图12.1.4-5展示了如何判断表情实体的样例：

![img](../img/chat-bot/clip_image184.jpg)

图12.1.4

![img](../img/chat-bot/clip_image186.jpg)

图12.1.5

注： LUIS的识别会去掉符号，目前测试发现通过企业微信程序发送的表情，LUIS可识别正确的意图（因为存在文字），而通过微信发送的表情无法识别（纯符号原因）。实体不会忽略掉文字符号。

 

 

 

 