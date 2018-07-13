## 元数据metadata：
## metadata元数据定义
元数据，又称元数据、中介数据、中继数据，为描述数据的数据，主要是描述数据属性的信息，用来支持如指示存储位置、历史数据、资源查找、文件纪录等功能。元数据算是一种电子式目录，为了达到编制目录的目的，必须在描述并收藏数据的内容或特色，进而达成协助数据检索的目的.
### <title>标签
定义浏览器工具栏中的标题
提供页面被添加到收藏夹时显示的标题
显示在搜索引擎结果中的页面标题

### <meta> 标签
提供关于 HTML 文档的元数据。元数据不会显示在页面上，但是对于机器是可读的。
典型的情况是，meta 元素被用于规定页面的描述、关键词、文档的作者、最后修改时间以及其他元数据。
content 是meta必须的属性，定义与 http-equiv 或 name 属性相关的元信息。
http-equiv ,name, scheme 是meta 可选的属性。（HTML5 不支持 scheme 属性）

​

#### http-equiv属性：

为名称/值对提供了名称。并指示服务器在发送实际的文档之前先在要传送给浏览器的 MIME 文档头部包含名称/值对。

当服务器向浏览器发送文档时，会先发送许多名称/值对。虽然有些服务器会发送许多这种名称/值对，但是所有服务器都至少要发送一个：content-type:text/html。这将告诉浏览器准备接受一个 HTML 文档。

使用带有 http-equiv 属性的 <meta> 标签时，服务器将把名称/值对添加到发送给浏览器的内容头部。

语法格式：<meta http-equiv="参数" content="参数变量值">

参数：

content-Type 描述文档类型，字符集

<meta http-equiv="expires" content="text/html; chartset=utf-8">

meta标签的charset的信息参数如GB2312时，代表说明网站是采用的编码是简体中文；
meta标签的charset的信息参数如BIG5时，代表说明网站是采用的编码是繁体中文；
meta标签的charset的信息参数如iso-2022-jp时，代表说明网站是采用的编码是日文；
meta标签的charset的信息参数如ks_c_5601时，代表说明网站是采用的编码是韩文；
meta标签的charset的信息参数如ISO-8859-1时，代表说明网站是采用的编码是英文；
meta标签的charset的信息参数如UTF-8时，代表世界通用的语言编码；
在 HTML5 中，有一个新的 charset 属性，它使字符集的定义更加容易：

<meta charset="UTF-8">

default-style规定要使用的预定义的样式表

<meta http-equiv="default-style" content="the document's preferred stylesheet">

其中content 属性的值必须匹配同一文档中的一个 link 元素上的 title 属性的值，或者必须匹配同一文档中的一个 style 元素上的 title 属性的值

expires 可以用于设定网页的到期时间。一旦网页过期，必须到服务器上重新传输（必须使用GMT的时间格式）

<meta http-equiv="expires" content="Wed, 20-Jun-2017 22:30:00 GTM">(必须使用GMT时间格式)

Refresh 自动刷新并指向新页面

<meta http-equiv="Refresh" content="2;URL=http://www.baidu.com/"> 表示2秒后跳到百度页面

值 "refresh" 应该慎重使用，因为它会使得页面不受用户控制。在 W3C's Web 内容可访问性指南 中使用 "refresh" 会到导致失败。

Set-Cookie cookie设定，如果网页过期，那么存盘的cookie将被删除

<meta http-equiv="Set-Cookie" content="cookievalue=xxx;expires=Wednesday,20-Jun-2017 22:30:00 GTM;path=/ ">(必须使用GMT时间格式)

Pragma是用于设定禁止浏览器从本地机的缓存中调阅页面内容，设定后一旦离开网页就无法从Cache中再调出

<meta http-equiv="Pragma" content="no-cache">访问者不能脱机浏览此网页

Window-target 显示窗口的设定，强制页面在当前窗口以独立页面显示

<meta http-equive="Window-target" content="_top"> 用来防止别人在框架中调用此页面

Page-Enter 和Page-Exit设定进入/离开页面时的特殊效果

<meta http-equiv="Page-Enter" content="revealTrans(duration=1.0,transtion=12)">

<meta http-equiv="Page-Exit" content="revealTrans(duration=1.0,transtion=12)">

duration的值为网页动态过渡的时间，单位为秒。

transition是过渡方式，它的值为0到23，分别对应24种过渡方式：

| 值 | 过渡方式 | 值 | 过渡方式 |
| :--: | :------------------: | :--: | :------------------: |
| 0 | 盒状收缩 | 1 | 盒状放射 |
| 2 | 圆形收缩 | 3 | 圆形放射 |
| 4 | 由上往下 | 5 | 由下往上 |
| 6 | 从左至右 | 7 | 从右至左 |
| 8 | 垂直百叶窗 | 9 | 水平百叶窗 |
| 10 | 水平格状百叶窗 | 11 | 垂直格状百叶窗 |
| 12 | 随意溶解 | 13 | 从左右两端向中间展开 |
| 14 | 从中间向左右两端展开 | 15 | 从上下两端向中间展开 |
| 16 | 从中间向上下两端展开 | 17 | 从右上角向左下角展开 |
| 18 | 从右下角向左上角展开 | 19 | 从左上角向右下角展开 |
| 20 | 从左下角向右上角展开 | 21 | 水平线状展开 |
| 22 | 垂直线状展开 | 23 | 随机产生一种过渡方式 |

cache-control`指定请求和响应遵循的缓存机制

Cache-Control指定请求和响应遵循的缓存机制。在请求消息或响应消息中设置Cache-Control并不会修改另一个消息处理过程中的缓存处理过程

请求时的缓存指令包括no-cache、no-store、max-age、max-stale、min-fresh、only-if-cached

响应消息中的指令包括public、private、no-cache、no-store、no-transform、must-revalidate、proxy-revalidate、max-age

Public指示响应可被任何缓存区缓存
Private指示对于单个用户的整个或部分响应消息，不能被共享缓存处理。这允许服务器仅仅描述当用户的部分响应消息，此响应消息对于其他用户的请求无效
no-cache指示请求或响应消息不能缓存
no-store用于防止重要的信息被无意的发布。在请求消息中发送将使得请求和响应消息都不使用缓存。
max-age指示客户机可以接收生存期不大于指定时间（以秒为单位）的响应
min-fresh指示客户机可以接收响应时间小于当前时间加上指定时间的响应
max-stale指示客户机可以接收超出超时期间的响应消息。如果指定max-stale消息的值，那么客户机可以接收超出超时期指定值之内的响应消息。
no-siteapp百度会自动对网页进行转码，这个标签是禁止百度的自动转码
<meta http-equiv="cache-control" content="no-cache">(在访问指着网站需要重新下载)

<meta http-equiv="Cache-Control" content="no-siteapp" />

content-Language显示语言的设定

<metahttp-equiv="Content-Language"content="zh-cn"/>

Content-Script-TypeW3C网页规范，指明页面中脚本的类型

<meta http-equiv="Content-Script-Type" Content="text/javascript">

Pics-label 网页等级评定

<meta http-equiv="Pics-label" contect="">

在IE的internet选项中有一项内容设置，可以防止浏览一些受限制的网站，而网站的限制级别就是通过meta属性来设置的

​

####name属性:

name属性主要用于描述网页，与之对应的属性值为content，content中的内容主要是便于搜索引擎机器人查找信息和分类信息用的。

语法格式：<meta name="参数" content="具体参数值值">

参数：

Keywords关键字，用来告诉搜索引擎网页的关键字是什么

<meta name="Keywords" content="HTML, CSS, JavaScript">

description描述，用来告诉搜索引擎网站的主要内容

<meta name="description" content="Free Web tutorials on HTML, CSS, XML" />

robots机器人向导，用来告诉搜索机器人哪些页面需要索引，哪些页面不需要索引

content的参数有all,none,index,noindex,follow,nofollow，默认是all。

all：文件将被检索，且页面上的链接可以被查询；
none：文件将不被检索，且页面上的链接不可以被查询；
index：文件将被检索；
follow：页面上的链接可以被查询；
noindex：文件将不被检索，但页面上的链接可以被查询；
nofollow：文件将被检索，但页面上的链接不可以被查询
<metaname="robots"content="none">

author 作者，标注网页的作者

<metaname="author"content="root,root@xxxx.com">

generator规定用于生成文档的一个软件包,不用于手写页面

<meta name="generator" content="FrontPage 4.0">

Copyright说明网站版权信息

<metaname="copyright"content="信息参数"/>

Revisit-after 重坊，通知搜索引擎多少天访问一次

＜meta name="revisit-after" content="7days">

viewport影响移动端页面布局

<meta name="viewport" content="width=device-width, initial-scale=1.0">

content 参数：

width viewport 宽度(数值/device-width)
height viewport 高度(数值/device-height)
initial-scale 初始缩放比例
maximum-scale 最大缩放比例
minimum-scale 最小缩放比例
user-scalable 是否允许用户缩放(yes/no)
application-name定义固定网站应用程序实例的名称。

<meta name="application-name" content="w3school" />

光标悬停在 Windows 任务栏的固定网站按钮上时，此名称将出现在工具提示中。该应用程序名称还将附加到固定网站应用程序实例的窗口标题中。

各浏览器meta

Microsoft Internet Explorer

<!-- 优先使用最新的ie版本 -->
<meta http-equiv="x-ua-compatible" content="ie=edge">

<!-- 是否开启cleartype显示效果 -->
<meta http-equiv="cleartype" content="on">
<meta name="skype_toolbar" content="skype_toolbar_parser_compatible">

<!-- Pinned Site -->

<!-- IE 10 / Windows 8 -->
<meta name="msapplication-TileImage" content="pinned-tile-144.png">
<meta name="msapplication-TileColor" content="#009900">

<!-- IE 11 / Windows 9.1 -->
<meta name="msapplication-config" content="ieconfig.xml">
Google Chrome

<!-- 优先使用最新的chrome版本 -->
<meta http-equiv="X-UA-Compatible" content="chrome=1" />
<!-- 禁止自动翻译 -->
<meta name="google" value="notranslate">
360浏览器

<!-- 选择使用的浏览器解析内核 -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
UC手机浏览器

<!-- 将屏幕锁定在特定的方向 -->
<meta name="screen-orientation" content="landscape/portrait">
<!-- 全屏显示页面 -->
<meta name="full-screen" content="yes">
<!-- 强制图片显示，即使是"text mode" -->
<meta name="imagemode" content="force">
<!-- 应用模式，默认将全屏，禁止长按菜单，禁止手势，标准排版，强制图片显示。 -->
<meta name="browsermode" content="application">
<!-- 禁止夜间模式显示 -->
<meta name="nightmode" content="disable">
<!-- 使用适屏模式显示 -->
<meta name="layoutmode" content="fitscreen">
<!-- 当页面有太多文字时禁止缩放 -->
<meta name="wap-font-scale" content="no">
QQ手机浏览器

<!-- 锁定屏幕在特定方向 -->
<meta name="x5-orientation" content="landscape/portrait">
<!-- 全屏显示 -->
<meta name="x5-fullscreen" content="true">
<!-- 页面将以应用模式显示 -->
<meta name="x5-page-mode" content="app">
Apple iOS

<!-- Smart App Banner -->
<meta name="apple-itunes-app" content="app-id=APP_ID,affiliate-data=AFFILIATE_ID,app-argument=SOME_TEXT">

<!-- 禁止自动探测并格式化手机号码 -->
<meta name="format-detection" content="telephone=no">

<!-- Add to Home Screen添加到主屏 -->
<!-- 是否启用 WebApp 全屏模式 -->
<meta name="apple-mobile-web-app-capable" content="yes">
<!-- 设置状态栏的背景颜色,只有在 “apple-mobile-web-app-capable” content=”yes” 时生效 -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">
<!-- 添加到主屏后的标题 -->
<meta name="apple-mobile-web-app-title" content="App Title">
Google Android

<meta name="theme-color" content="#E64545">
<!-- 添加到主屏 -->
<meta name="mobile-web-app-capable" content="yes">
<!-- More info: https://developer.chrome.com/multidevice/android/installtohomescreen -->
App Links

<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="App Links">
<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="App Links">
<meta property="al:android:package" content="org.applinks">
<!-- Web Fallback -->
<meta property="al:web:url" content="http://applinks.org/documentation">
<!-- More info: http://applinks.org/documentation/ -->
常用的移动端meta

<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no" />
<meta name="apple-mobile-web-app-capable" content="yes" />
<meta name="apple-mobile-web-app-status-bar-style" content="black" />
<meta name="format-detection"content="telephone=no, email=no" />
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no" />
<meta name="apple-mobile-web-app-capable" content="yes" /><!-- 删除苹果默认的工具栏和菜单栏 -->
<meta name="apple-mobile-web-app-status-bar-style" content="black" /><!-- 设置苹果工具栏颜色 -->
<meta name="format-detection" content="telphone=no, email=no" /><!-- 忽略页面中的数字识别为电话，忽略email识别 -->
<!-- 启用360浏览器的极速模式(webkit) -->
<meta name="renderer" content="webkit">
<!-- 避免IE使用兼容模式 -->
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<!-- 针对手持设备优化，主要是针对一些老的不识别viewport的浏览器，比如黑莓 -->
<meta name="HandheldFriendly" content="true">
<!-- 微软的老式浏览器 -->
<meta name="MobileOptimized" content="320">
<!-- uc强制竖屏 -->
<meta name="screen-orientation" content="portrait">
<!-- QQ强制竖屏 -->
<meta name="x5-orientation" content="portrait">
<!-- UC强制全屏 -->
<meta name="full-screen" content="yes">
<!-- QQ强制全屏 -->
<meta name="x5-fullscreen" content="true">
<!-- UC应用模式 -->
<meta name="browsermode" content="application">
<!-- QQ应用模式 -->
<meta name="x5-page-mode" content="app">
<!-- windows phone 点击无高光 -->
<meta name="msapplication-tap-highlight" content="no">
<!-- 适应移动端end -->