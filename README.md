# AI_Identify_card：寻卡通
# Product Requirements：产品需求

Title | content
---|---
Target release(发布日期) | 2018/12/29
Epic(史诗名称) | 寻物通（高校学生在校遗失物寻找辅助器）
Document status(文档状态) | 已基本完成
Document owner( 文件的主人) | [Cherry婵](https://github.com/CherryLiChan)
Designer( 领头的设计师) | [Cherry婵](https://github.com/CherryLiChan)
Developer( 领头的开发者) | [Cherry婵](https://github.com/CherryLiChan)
QA(领头的测试者) | [Cherry婵](https://github.com/CherryLiChan)

## Table of contents
产品PRD | 产品原型 | 产品使用关键AI或机器学习之API的输出入展示
---|--- | ---
[产品简介](#Introduction) | [使用者交互及设计](#User-interaction-and-design) | [API输入与输出](#API输入与输出)
[目标](#Goals) | [产品功能架构](#产品功能架构) | [自定义模板文字识别API](#自定义模板文字识别API)
[背景](#Background) | [流程图](#流程图) | [具体自定义步骤及代码](#具体自定义步骤及代码)
[战略契合处](#strategic-fit) | [全局说明](#全局说明) | [特别注意](#特别注意)
[情境假设](#Assumptions) | [Axure交互及设计低保真原型](#Axure交互及设计低保真原型) | [API1.使用水平：API之输入及输出](#使用水平：API之输入及输出)
[用户画像](#User-portrait) | [原型1.交互及界面设计](#原型1.交互及界面设计&原型2.信息设计) | [API2.使用比较分析](#API2.使用比较分析)
[需求](#Requirements) | [原型2.信息设计](#原型1.交互及界面设计&原型2.信息设计)  | [API3.使用后风险报告](API3.使用后风险报告)
[问题](#Questions) | [原型3.原型文档](#原型1.交互及界面设计&原型2.信息设计)  | [API4.加分项](API4.加分项)
[不做](#Not-doing) | 
[迭代](#迭代) | 
[PRD1.加值宣言](#PRD1加值宣言)
[PRD2.核心价值](#PRD2核心价值)
[PRD3.核心价值与用户痛点](#PRD3核心价值与用户痛点)
[PRD4.人工智能概率性与用户痛点](#PRD4人工智能概率性与用户痛点)
[PRD5.需求列表与人工智能API加值](#PRD5需求列表与人工智能API加值)

# Introduction
> 寻物通是一款为丢失卡证/物品的人寻回饭卡，为捡到卡证/物品的人找到失主，致力于为丢失主与拾取者搭建联系桥梁的人工智能API应用产品。

# Goals
> - 在保留传统的高校失物招领功能的基础上,加大失物招领的找寻范围,加快失物找回效率的同时加深同学们的失物找回意识。
> - 为丢失主与拾取者之间搭建快速联系桥梁。通过信息识别、匹配，让卡证/物品失主轻松、及时找回自己的物品，让卡证/物品拾取者快速找到失主。从而降低物品丢/拾两者寻找对方的阻力。

# Background
> - 在过去信息不发达的时候,我们丢失物品不管重不重要,或多或少都会对我们产生影响,那时候科学技术不发达,信息的传播速度慢,丢失的物品通常是不易寻回的。更严重的是一旦丢失的身份证等重要物件被不法分子利用,失主很可能会遭到巨大的损失。而如今，科学技术已有了极大的进步，加上人工智能API的出现与发展，给了我们更好、更快地帮助同学们找回丢失的物品的条件。
>   - 摘自：[高校失物招领网络平台的发展与管理](http://kns.cnki.net/KXReader/Detail?TIMESTAMP=636825361153921250&DBCODE=CJFD&TABLEName=CJFDTEMP&FileName=GDCY201812079&RESULT=1&SIGN=zpS2mV2GfIJXYJH29uYKXkdkeD4%3d&UID=WEEvREcwSlJHSldRa1FhdkJkVG1CTTVTMmx6cnJzSkRibUxUZlpnODZJQT0=$9A4hF_YAuvQ5obgVAqNKPCYcEjKensW4IQMovwHtwkF4VYPoHbKxJw!!&filetitle=%e9%ab%98%e6%a0%a1%e5%a4%b1%e7%89%a9%e6%8b%9b%e9%a2%86%e7%bd%91%e7%bb%9c%e5%b9%b3%e5%8f%b0%e7%9a%84%e5%8f%91%e5%b1%95%e4%b8%8e%e7%ae%a1%e7%90%86_%e7%8e%8b%e5%b0%9a%e6%9d%b0)

> - 根据[《大学校园失窃现象调查报告分析》](http://www.docin.com/p-588153652.html)显示：
>   - 学生丢失东西的价值主要集中在50元以下（饭卡、雨伞等就在此价格区间内）。
> - 根据[《关于青岛高校学生在校遗失物调查报告》](http://www.docin.com/p-441578603.html?qq-pf-to=pcqq.c2c)显示：
>   - 绝大部分的高校学生都会丢失物品,且对于丢失物品如何找回的意识比较差,丢失的东西通常抱着“自己找找如果找不到就重新买一个”的想法。而在近几年，不少失主开始在朋友圈里发布各种寻物启事和失物招领的信息，而很多时候，由于个人圈子的局限性，起到的效果并不是很乐观。这份报告里提到，==70%的同学在物品遗失后没有寻回来==。
>       - ![朋友圈找饭卡](https://note.youdao.com/yws/api/personal/file/97A8C3508D9044A5A44AE4F8DA476A19?method=download&shareKey=81e350318b2449f9bc8b0f8f5ba8c318)
>       - ![为找回饭卡写的超强文案](https://note.youdao.com/yws/api/personal/file/06DEE52B1BC341F1A94C58EFDA7C790A?method=download&shareKey=afc6a71820a2ced35709925dcfa6233b)
>   - 报告还表明:63%的同学认为遗失物难以寻回的原因是客观方面的原因。其中一方面就是==缺少机构来帮助失主寻回遗失物，并且在失主和拾获者之间难以建立联系==（在某些情况下，拾获者寻找失主也是存在一定困难的）。
>   - 事实上，同学们对于丢失的东西还是很希望能够找到的,毕竟失而复得确实是一件让人高兴的一件事。全日制高校对失物招领工作其有着一定需求,以及适宜其发展、成长的土壤,存在着市场空白。在增加失物找回的概率和降低同学们的损失、节约同学们的宝贵时间等方面，人工智能API应用产品《寻物通》是个不错的选择。

# strategic-fit
1. 本产品通过让用户输入学号姓名头像等信息搭建数据库
2. 拾获者把自己捡到的遗失物拍照上传后，本产品通过文本/图像识别技术，识别卡照片上的信息，然后进行信息抽取、分类，并与后台数据库相关类匹配，找到失主。
3. 发送信息告知失主遗失物已被捡到。在失主和拾获者之间搭建临时对话框，方便两者交流。

# Assumptions
- 用户需要在手机上联网使用本产品。
- 用户在使用上传功能时，需要给出摄像头权限。
- 用户如果想要收到丢失信息，必须在数据库里拥有一席之地，即先登记信息。需要给出信息通知权限。
- 所用技术：Python、文本识别API、信息提取和分类、入库检索、精准匹配。

# User-portrait

类别 | 详情
---|---
群体 | 高校大学生群体
年龄 | 18-25岁
习惯 | 1. 丢三落四、容易丢东西；2.热心肠、经常捡到遗失物品
痛点 | 1.找不到遗失物品；2.找不到失主
pic | ![用户画像](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1546925268058&di=bc3f1137d986f8fb32d11eb7599d87f5&imgtype=0&src=http%3A%2F%2Fpic38.huitu.com%2Fres%2F20151015%2F799232_20151015203415767400_1.jpg)![使用饭卡](https://tse1-mm.cn.bing.net/th?id=OIP.TVMEb_cGdhajYYnwrB5THwHaFj&w=256&h=190&c=7&o=5&dpr=1.1&pid=1.7)

# Requirements
＃ | 标题 | 用户案例 | 重要程度 | 笔记
---|---|---|---|---
1 | 个人物品不见了！ | 用户A一不小心把个人物品弄丢了，立刻来本平台登记丢失信息，静候信息 | 必须有 | 搭建数据库存储信息
2 | 捡到遗失物品！ | 用户B捡到某同学的遗失物，立刻来本平台上传相关图片信息，把相关信息上传到平台后台 | 必须有 | API识别、信息提取、分类、入库检索等技术
3 | 1、2数据匹配 | 后台数据库匹配信息一致，发起临时对话框，并发送提醒信息告知用户 | 必须有 | 信息配对、通知权限

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
- 遗失者
- 拾获者

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
问题 | 成果
---|---
找不到遗失物 | 快速收到信息并找回
找不到失主 | 快速找到失主

# Not-doing
1. 数据信息匹配。

# 迭代
1. [搭建 页面 及 数据库](https://github.com/CherryLiChan/LostAndFound)
2. 实现 遗失者 [上传、信息识别提取分类功能](#API输入与输出)
3. 实现 拾捡者 [上传、信息识别提取分类功能](#API输入与输出)
4. 实现 2、3两点 获得的[数据匹配](#API输入与输出)
5. 为 丢-捡 双方创建联系桥梁

# API输入与输出
## 1.百度-自定义模板文字识别API
卡类（饭卡）丢失物内容识别
#### [具体自定义步骤及代码](https://github.com/CherryLiChan/API_ML_AI/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF%E6%96%87%E5%AD%97%E8%AF%86%E5%88%AB%E8%AF%B4%E6%98%8E.md)

## 2.百度-图像搜索-相同/相似图片搜索API
非卡类丢失物入库与检索
#### [详细代码示例](https://github.com/CherryLiChan/API_ML_AI/blob/master/python-code-pic.ipynb)

## 3.百度-通用图像分析-通用物体和场景识别API
自动识别上传的图片里的物品的种类，并取出识别结果，做成产品的分类标签，自动归类用户丢失/拾取到的物品。
#### [详细代码示例](https://github.com/CherryLiChan/API_ML_AI/blob/master/python-code-tag.ipynb)

# 评分量表
## PRD1加值宣言
- 自定义模板文字识别API对本产品加值部分在于：
  - 解放双手，不需要用户逐个缓慢的输入相关信息，只需要上传照片即可把相关信息识别出来。
  - 此信息可以分类放入数据库，方便后台匹配信息，快速找到失主/拾捡者。
- 相同/相似图片搜索API对本产品加值部分在于：
  - 轻松将非卡类丢失物放入库，并提供检索功能（类似于"淘宝扫一扫"的"拍立淘"功能），以便查找匹配找回丢失物/找到失主。
- 通用物体识别API对本产品加值部分在于：
  - 自动识别上传的图片里的物品的种类，并取出识别结果，做成产品的分类标签，自动归类用户丢失/拾取到的物品。
- 产品文档中“[需求](#Requirements)”及“[背景](#Background)”“[战略契合处](#strategic-fit)”有反映。

## PRD2核心价值
- 最小可用产品（产品核心价值）为识别、提取照片上的有用信息，分类放入库并实现库物品的检索。目前[相关代码](#API输入与输出)已实现。

## PRD3核心价值与用户痛点
- 解决 “找回遗失物品难”和“找不到失主” 的日常校园痛点问题。
- 产品文档中“[需求](#Requirements)”及“[背景](#Background)”“[战略契合处](#strategic-fit)”有反映。

## PRD4人工智能概率性与用户痛点
- 自定义模板文字识别已进行训练，在[API使用流程说明](https://github.com/CherryLiChan/API_ML_AI/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF%E6%96%87%E5%AD%97%E8%AF%86%E5%88%AB%E8%AF%B4%E6%98%8E.md)可见训练结果。
- 预估准确率为94.44%，对用户体验的负面影响不会压过正面影响的机率。有效解决产品的核心价值和痛点问题。

## PRD5需求列表与人工智能API加值
- 产品文档中“[需求](#Requirements)”部分有反映使用的API加值，
- 用到的的api有文本识别、信息提取、分类、信息匹配，

## 原型1.交互及界面设计 & 原型2.信息设计 & 原型文档
- [产品原型展示和信息设计](http://cherry_chan.gitee.io/api_ml_ai_axure_prototype/#g=1)，包括交互及界面设计、信息设计、原型文档的所有内容。
- [Gitee-原型下载地址](https://gitee.com/Cherry_Chan/api_ml_ai_axure_prototype)
- 人工智能的加值部分在原型文档 2.1捡到登记页, 2.2丢失登记页, 3.2系统信息。

## 使用水平：API之输入及输出
- [自定义模板文字识别API使用流程说明](https://github.com/CherryLiChan/API_ML_AI/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF%E6%96%87%E5%AD%97%E8%AF%86%E5%88%AB%E8%AF%B4%E6%98%8E.md)
- [所有API输入输出代码](#API输入与输出)

##### API1.使用水平
- 输入：遗失物品图片；输出：遗失物品识别信息
- 输入：遗失物品识别信息；输出：后台数据库收集数据、前端发布信息
- 输入：信息成功匹配；输出：系统信息告知用户
- [所有API输入输出代码](#API输入与输出)

#### API2.使用比较分析
- [阿里云-自定义模板](https://help.aliyun.com/document_detail/89067.html)
- [百度AI开放平台-自定义模板文字识别](https://ai.baidu.com/tech/ocr/iocr)
- 目前百度的自定义模板文字识别比较常被使用，所以这产品调用了百度AI开放平台的自定义模板文字识别。

对比项 | 阿里云 | 百度
---|---|---
成熟度 | [使用教程完善](https://help.aliyun.com/document_detail/89067.html?spm=a2c4g.11186623.6.565.6b4d7bce7KfMJI)、但[API文档较不完善](https://help.aliyun.com/document_detail/88944.html?spm=a2c4g.11186623.6.556.2e354390eVUSAu) | [文档清晰且详细](http://ai.baidu.com/iocr/#/helpcenter)，预估准确率达到94.44%
性价比 | [0元/500次,238元/1000次,2008元/1W次](https://market.aliyun.com/products/57124001/cmapi029975.html?spm=5176.11065268.1996646101.searchclickresult.6d954064JXtAAt#sku=yuncode2397500009)等 | 500次/天免费，但[付费开通项](https://console.bce.baidu.com/ai/?fromai=1#/ai/ocr/overview/index)显示完全免费

#### API3.使用后风险报告
- 自定义模板文字识别已进行训练，在[API使用流程说明](https://github.com/CherryLiChan/API_ML_AI/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF%E6%96%87%E5%AD%97%E8%AF%86%E5%88%AB%E8%AF%B4%E6%98%8E.md)可见训练结果。
- 预估准确率为94.44%，对用户体验的负面影响不会压过正面影响的机率。

对比项 | 阿里云 | 百度 | 总结
---|---|---|---
API市场竞争程度 | bing搜索排行为第五 | bing搜索排行前五都有 | 市面上百度的应用与使用教程较多，说明百度更有市场优势
输入输出限制 | 输入图片输出框定的文字内容 | 输入图片输出框定的文字内容 | 输入输出全靠自己的设定（自定义），无法比较
定价 | [0元/500次,238元/1000次,2008元/1W次](https://market.aliyun.com/products/57124001/cmapi029975.html?spm=5176.11065268.1996646101.searchclickresult.6d954064JXtAAt#sku=yuncode2397500009)等 | 500次/天免费，但[付费开通项](https://console.bce.baidu.com/ai/?fromai=1#/ai/ocr/overview/index)显示完全免费 | 都是500次/天免费，没试过超额，暂时不知道百度超额后是否仍可用，暂无法比较

#### API4.加分项
- 用到的的api有自定义模板文字识别API、相同/相似图片搜索API、通用物体和场景识别API，做到卡类遗失物的文本内容提取、物品归类、非卡类遗失物入库与检索，具体如下：
- [自定义模板文字识别API使用流程说明](https://github.com/CherryLiChan/API_ML_AI/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF%E6%96%87%E5%AD%97%E8%AF%86%E5%88%AB%E8%AF%B4%E6%98%8E.md)
- [所有API输入输出代码](#API输入与输出)
