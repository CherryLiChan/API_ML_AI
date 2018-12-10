# AI_Identify_card：寻卡通
# Product Requirements：产品需求

Title | content
---|---
Target release(发布日期) | 2018/12/1
Epic(史诗名称) | 寻卡通（证件/饭卡寻找辅助器）
Document status(文档状态) | 进行中
Document owner( 文件的主人) | [Cherry婵](https://github.com/CherryLiChan)
Designer( 领头的设计师) | [Cherry婵](https://github.com/CherryLiChan)
Developer( 领头的开发者) | [Cherry婵](https://github.com/CherryLiChan)
QA(领头的测试者) | [Cherry婵](https://github.com/CherryLiChan)

## Table of contents
- [产品介绍](#Introduction)
- [目标](#Goals)
- [背景](#Background)
- [战略契合处](#strategic-fit) 
- [情境假设](#Assumptions)
- [用户画像](#User-portrait)
- [需求](#Requirements)
- [使用者交互及设计](#User-interaction-and-design)
  - [产品功能架构](#产品功能架构)
  - [流程图](#流程图)
  - [全局说明](#全局说明)
  - [Axure交互及设计低保真原型](#Axure交互及设计低保真原型)
- [问题](#Questions)
- [不做](#Not-doing)
- [迭代](#迭代)
- [API输入与输出](#API输入与输出)
  - [自定义模板文字识别API](#自定义模板文字识别API)
    - [具体自定义步骤及代码](#具体自定义步骤及代码)
    - [特别注意](#特别注意)
- [评分量表](#评分量表)
  - [PRD1.加值宣言](#PRD1加值宣言)
  - [PRD2.核心价值](#PRD2核心价值)
  - [PRD3.核心价值与用户痛点](#PRD3核心价值与用户痛点)
  - [PRD4.人工智能概率性与用户痛点](#PRD4人工智能概率性与用户痛点)
  - [PRD5.需求列表与人工智能API加值](#PRD5需求列表与人工智能API加值)
  - [原型1.交互及界面设计&原型2.信息设计](#原型1.交互及界面设计&原型2.信息设计)
  - [使用水平：API之输入及输出](#使用水平：API之输入及输出)

# Introduction
> 寻卡通是一款为丢失证件/饭卡的人寻回饭卡，为捡到饭卡的人找到失主，致力于为丢失主与拾取者搭建联系桥梁的人工智能API应用产品。

# Goals
> 为丢失主与拾取者之间搭建快速联系桥梁。通过信息识别、匹配，让证件/饭卡失主轻松、及时找回自己的物品，让证件/饭卡拾取者快速找到失主。从而降低物品丢/拾两者寻找对方的阻力。

# Background
- 在如今的大学校园里，每个学生都会拥有一张学校提供的饭卡，这张卡让他们得以去饭堂吃饭、去图书卡借书、去快递点取快递，同时这张饭卡也能证明它的主人的学生身份。

- 然而这张小但重要的卡却经常会在不经意间被它的主人丢失。

- 而拾到饭卡的同学，却经常因为没有饭卡失主的联系方式而找不到失主。

- 两者的联系渠道的缺失导致了饭卡资源的浪费。

- ![朋友圈找饭卡](https://note.youdao.com/yws/api/personal/file/97A8C3508D9044A5A44AE4F8DA476A19?method=download&shareKey=81e350318b2449f9bc8b0f8f5ba8c318)
- ![为找回饭卡写的超强文案](https://note.youdao.com/yws/api/personal/file/06DEE52B1BC341F1A94C58EFDA7C790A?method=download&shareKey=afc6a71820a2ced35709925dcfa6233b)

# strategic-fit
1. 本产品通过让用户输入学号姓名头像等信息搭建数据库
2. 拾卡者把自己捡到的卡拍照上传后，本产品通过文本识别技术，识别卡上的信息，然后进行信息抽取、分类，并与后台数据库相关类匹配，找到失主。
3. 发送信息告知失主饭卡已被捡到。在失主和拾取者之间搭建临时对话框，方便两者交流。

# Assumptions
- 用户需要在手机上联网使用本产品。
- 用户在使用上传功能时，需要给出摄像头权限。
- 用户如果想要收到丢失信息，必须在数据库里拥有一席之地，即先登记信息。需要给出信息通知权限。
- 所用技术：Python、文本识别API、信息提取和分类、精准匹配。

# User-portrait
拥有饭卡、丢失饭卡、见到饭卡的在校大学生或公司员工。

![使用饭卡](https://tse1-mm.cn.bing.net/th?id=OIP.TVMEb_cGdhajYYnwrB5THwHaFj&w=256&h=190&c=7&o=5&dpr=1.1&pid=1.7)

# Requirements
＃ | 标题 | 用户案例 | 重要程度 | 笔记
---|---|---|---|---
1 | 卡不见了！ | 用户A一不小心把饭卡弄丢了，立刻来本平台登记丢失信息，静候信息 | 必须有 | 搭建数据库存储信息
2 | 捡到卡啦！ | 用户B捡到一张饭卡，立刻来本平台上传相关图片信息，把捡到的卡上的相关信息上传到平台后台 | 必须有 | API文本识别、信息提取、分类等技术
3 | 1、2数据匹配 | 后台数据库匹配到两人发送的学号、姓名等信息相匹配，发起临时对话框，并发送提醒信息告知用户 | 必须有 | 信息配对、通知权限

# User-interaction-and-design

## 产品功能架构
![产品功能架构图](https://note.youdao.com/yws/api/personal/file/EF0E2F6E2EA8436E86CB520852C3B969?method=download&shareKey=c76e893b0711646b4975dfa4d2fa0a1e)

## 流程图
![流程图](https://note.youdao.com/yws/api/personal/file/6C072CDD1CDD4192A16F3E7DD2B0DFDC?method=download&shareKey=d4ddf93ecffa5edeba7c989fe367835b)

## 全局说明
1. 功能权限分为登录/未登录两个状态：
- 登录：登录状态下才可能收到信息。
- 未登录：无法收到收到信息。

2. 用户兼具两个角色：
- 丢失者
- 拾捡者

3. 底部导航栏：
- 首页：搜索信息、寻找信息
- “+”号FAB菜单：点击后弹出“丢”和“捡”两个选项。
- 我的：个人中心、个人信息、个人设置、临时对话框页面

4. 键盘说明
- 点击注册/登陆输入框时弹出数字键盘
- 点击搜索输入框时弹出字母键盘

3. 登录页面/用户注册页面：
最好通过第三方或者手机登陆；

4. 上传功能
需调用手机摄像头。

## [Axure交互及设计低保真原型](http://cherry_chan.gitee.io/api_ml_ai_axure_prototype)
![产品交互及设计低保真原型](https://note.youdao.com/yws/api/personal/file/B72A932213974366B0A12CFB812D477A?method=download&shareKey=8e08fb597166cd11cb58102ae897a70d)

# Questions
列出以上需求文件做完旳话可以完成什麽样的问题

问题 | 成果
---|---
找不到卡 | 快速收到信息，找回卡
找不到失主 | 快速找到失主

# Not-doing
1. 其他物品的 丢 - 捡。

# 迭代
1. 搭建 页面 及 数据库
2. 实现 遗失者 上传、信息识别提取分类功能
3. 实现 拾捡者 上传、信息识别提取分类功能
4. 实现 2、3两点 获得的数据匹配
5. 为 丢-捡 双方创建联系桥梁

# API输入与输出
## 自定义模板文字识别API
1. 所需API：百度 自定义模板文字识别API
2. 调用代码：查看[API文档](https://ai.baidu.com/docs#/OCR-API/4cf952fc)，[通过API Key和Secret Key获取的access_token](http://ai.baidu.com/docs#/Auth/top)。
3. 上传一张 饭卡 的图片作为模板（用于制作模板的图片要求摆放端正、平整，拍摄时避免过曝，阴影等不良情况），然后在模板上框选一些固定的字段 如“姓名、学号、院系”等 信息作为【参照字段】。
3. 提交 Api Key 和 Secret Key
4. 读取 access_token 返回的信息，在代码这一块：用 json.load() 把返回的信息转成字典
5. 复制 access_token 返回的信息，组合并调用，打开本地相册文件（要识别的饭卡）
6. 把处理好的 img 和之前获得的 access_token 放入一个字典里，并提交给网址(https://aip.baidubce.com/rest/2.0/solution/v1/iocr/recognise)，它会以 json 格式返回一个分析结果给我们。（得到需要分类放入数据库的信息）

#### [具体自定义步骤及代码](https://github.com/CherryLiChan/API_ML_AI/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF%E6%96%87%E5%AD%97%E8%AF%86%E5%88%AB%E8%AF%B4%E6%98%8E.md)：
- 在 Chrome 中打开 ai.baidu.com/iocr 进入模板管理界面，
- 此时需要首先登陆百度账号（和百度网盘、百度贴吧、百度文库等百度系产品通用），
- 进入后点击创建模板，进入模板编辑界面，首先需要给模板进行命名，然后点击左侧编辑框中的按钮上传模板图片（模板图片要求端正、清晰），
- 然后框选字段值，框选后在右侧对应位置填写字段名，全部框选完后点击右侧“参照字段”标签，在图中框选参照字段，完成后点击保存，则已经制作完模板，
- 此时可以点击“发布”按钮，把次模板发布到线上环境（保存只是保存修改记录，不会实时生效，发布后您的所有操作才会生效），
- 然后可以参照文档中的“请求说明”上传图片，并制定templateSign（模板标识），来指定上传的图片使用该模板。

#### 特别注意：
上传用于模板制作的图片，
- 最大：小于等于4M，且分辨率小于等于4096像素乘4096像素，
- 最小：大于等于15像素乘15像素且大于等于1KB，
- 后期上传识别的图片最大：大小不超过4M，且分辨率小于等于4096像素乘4096像素，
- 最小：大于等于15像素乘15像素且大于等于1KB。

# 评分量表
## PRD1加值宣言
- 自定义模板文字识别API对本产品加值部分在于：1.解放双手，不需要用户逐个缓慢的输入相关信息，只需要上传照片即可把相关信息识别出来。2.此信息可以分类放入数据库，方便后台匹配信息，快速找到失主/拾捡者。
- 产品文档中“需求”及“背景”“战略契合处”有反映。

## PRD2核心价值
- 最小可用产品为识别并提取饭卡上的相关信息。

## PRD3核心价值与用户痛点
- 解决 “找回饭卡难”和“找不到失主” 的日常校园痛点问题。
- 产品文档中“需求”及“背景”“战略契合处”有反映。

## PRD4人工智能概率性与用户痛点
- 自定义模板文字识别已进行训练，在[API使用流程说明](https://github.com/CherryLiChan/API_ML_AI/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF%E6%96%87%E5%AD%97%E8%AF%86%E5%88%AB%E8%AF%B4%E6%98%8E.md)可见训练结果。
- 预估准确率为94.44%，对用户体验的负面影响不会压过正面影响的机率。

## PRD5需求列表与人工智能API加值
- 产品文档中“需求”部分有反映使用的API加值，
- 用到的的api有文本识别、信息提取、分类、信息匹配，

## 原型1.交互及界面设计&原型2.信息设计
- [产品原型展示](http://cherry_chan.gitee.io/api_ml_ai_axure_prototype/#g=1)
- [Gitee-原型下载地址](https://gitee.com/Cherry_Chan/api_ml_ai_axure_prototype)

## 使用水平：API之输入及输出
- [API使用流程说明](https://github.com/CherryLiChan/API_ML_AI/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF%E6%96%87%E5%AD%97%E8%AF%86%E5%88%AB%E8%AF%B4%E6%98%8E.md)
- [API输入输出代码](https://github.com/CherryLiChan/API_ML_AI/blob/master/python-code.ipynb)

##### API1.使用水平
- [API输入输出代码](https://github.com/CherryLiChan/API_ML_AI/blob/master/python-code.ipynb)

#### API2.使用比较分析
- [阿里云-自定义模板](https://help.aliyun.com/document_detail/89067.html)
- [百度AI开放平台-自定义模板文字识别](https://ai.baidu.com/tech/ocr/iocr)
- 目前百度的自定义模板文字识别比较常被使用，所以这产品调用了百度AI开放平台的自定义模板文字识别。

#### API3.使用后风险报告
- 自定义模板文字识别已进行训练，在[API使用流程说明](https://github.com/CherryLiChan/API_ML_AI/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF%E6%96%87%E5%AD%97%E8%AF%86%E5%88%AB%E8%AF%B4%E6%98%8E.md)可见训练结果。
- 预估准确率为94.44%，对用户体验的负面影响不会压过正面影响的机率。

#### API4.加分項
- 用到的的api有文本识别、信息提取、分类、信息匹配
