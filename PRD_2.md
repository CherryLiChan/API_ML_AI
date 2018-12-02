# Product Requirements：产品需求

Title | content
---|---
Target release(发布日期) | 2018/12/1
Epic(史诗名称) | 寻卡通（证件/饭卡寻找辅助器）
Document status(文档状态) | 进行中
Document owner( 文件的主人) | Cherry婵
Designer( 领头的设计师) | Cherry婵
Developer( 领头的开发者) | Cherry婵
QA(领头的测试者) | Cherry婵

# 产品介绍
寻卡通是一款为丢失证件/饭卡的人寻回饭卡，为捡到饭卡的人找到失主，致力于为丢失主与拾取者搭建联系桥梁的人工智能API应用产品。

# Goals: 目标
为丢失主与拾取者之间搭建快速联系桥梁。通过信息识别、匹配，让证件/饭卡失主轻松、及时找回自己的物品，让证件/饭卡拾取者快速找到失主。从而降低物品丢/拾两者寻找对方的阻力。

# Background: 背景
在如今的大学校园里，每个学生都会拥有一张学校提供的饭卡，这张卡让他们得以去饭堂吃饭、去图书卡借书、去快递点取快递，同时这张饭卡也能证明它的主人的学生身份。

然而这张小但重要的卡却经常会在不经意间被它的主人丢失。

而拾到饭卡的同学，却经常因为没有饭卡失主的联系方式而找不到失主。

两者的联系渠道的缺失导致了饭卡资源的浪费。

![朋友圈找饭卡](https://note.youdao.com/yws/api/personal/file/97A8C3508D9044A5A44AE4F8DA476A19?method=download&shareKey=81e350318b2449f9bc8b0f8f5ba8c318)
![为找回饭卡写的超强文案](https://note.youdao.com/yws/api/personal/file/06DEE52B1BC341F1A94C58EFDA7C790A?method=download&shareKey=afc6a71820a2ced35709925dcfa6233b)

# strategic fit: 战略契合处
1. 本产品通过让用户输入学号姓名头像等信息搭建数据库
2. 拾卡者把自己捡到的卡拍照上传后，本产品通过文本识别技术，识别卡上的信息，然后进行信息抽取、分类，并与后台数据库相关类匹配，找到失主。
3. 发送信息告知失主饭卡已被捡到。在失主和拾取者之间搭建临时对话框，方便两者交流。

# Assumptions: 情境假设
- 用户需要在手机上联网使用本产品。
- 用户在使用上传功能时，需要给出摄像头权限。
- 用户如果想要收到丢失信息，必须在数据库里拥有一席之地，即先登记信息。需要给出信息通知权限。
- 所用技术：Python、文本识别API、信息提取和分类、精准匹配。

# User portrait：用户画像
拥有饭卡、丢失饭卡、见到饭卡的在校大学生或公司员工。

![使用饭卡](https://tse1-mm.cn.bing.net/th?id=OIP.TVMEb_cGdhajYYnwrB5THwHaFj&w=256&h=190&c=7&o=5&dpr=1.1&pid=1.7)

# Requirements：需求
＃ | 标题 | 用户案例 | 重要程度 | 笔记
---|---|---|---|---
1 | 卡不见了！ | 用户A一不小心把饭卡弄丢了，立刻来本平台登记丢失信息，静候信息 | 必须有 | 搭建数据库存储信息
2 | 捡到卡啦！ | 用户B捡到一张饭卡，立刻来本平台上传相关图片信息，把捡到的卡上的相关信息上传到平台后台 | 必须有 | API文本识别、信息提取、分类等技术
3 | 1、2数据匹配 | 后台数据库匹配到两人发送的学号、姓名等信息相匹配，发起临时对话框，并发送提醒信息告知用户 | 必须有 | 信息配对、通知权限

# User interaction and design：使用者交互及设计

## 产品功能架构
![产品功能架构图](https://note.youdao.com/yws/api/personal/file/EF0E2F6E2EA8436E86CB520852C3B969?method=download&shareKey=c76e893b0711646b4975dfa4d2fa0a1e)

## 流程图
![流程图](https://note.youdao.com/yws/api/personal/file/6C072CDD1CDD4192A16F3E7DD2B0DFDC?method=download&shareKey=d4ddf93ecffa5edeba7c989fe367835b)

## 全局说明
功能权限分为登录/未登录两个状态：
- 登录：登录状态下才可能收到信息。
- 未登录：无法收到收到信息。

用户兼具两个角色：
- 丢失者
- 拾捡者

底部导航栏：
- 首页：搜索信息、寻找信息
- “+”号FAB菜单：点击后弹出“丢”和“捡”两个选项。
- 我的：个人中心、个人信息、个人设置、临时对话框页面

## Axure交互及设计低保真原型
![产品交互及设计低保真原型](https://note.youdao.com/yws/api/personal/file/B72A932213974366B0A12CFB812D477A?method=download&shareKey=8e08fb597166cd11cb58102ae897a70d)

# Questions：问题
列出以上需求文件做完旳话可以完成什麽样的问题

问题 | 成果
---|---
找不到卡 | 快速收到信息，找回卡
找不到失主 | 快速找到失主

# Not doing：不做
1. 其他物品的 丢 - 捡。

# 迭代
1. 搭建 页面 及 数据库
2. 实现 遗失者 上传、信息识别提取分类功能
3. 实现 拾捡者 上传、信息识别提取分类功能
4. 实现 2、3两点 获得的数据匹配
5. 为 丢-捡 双方创建联系桥梁