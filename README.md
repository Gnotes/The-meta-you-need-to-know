# The-meta-you-need-to-know

> **Meta** 在 HTML 中大家都知道是用来描述页面信息的，但是具体有哪些呢？各自的使用方式及参数是什么呢，或许跟我现在一样 ~懵逼~

## 前言

在说 meta 之前我们先来了解下 `Metadata`，翻译过来是 **元数据**，是描述数据的数据(data about data)，用于描述数据属性（property）的信息，_在 HTML 中就是描述页面属性的一些描述信息_ [百度百科](https://baike.baidu.com/item/%E5%85%83%E6%95%B0%E6%8D%AE/1946090)

## Meta 能做些什么

Meta 常用于搜索引擎优化（SEO），定义页面编码语言(UTF-8)，页面缓存控制...(看完就明白了)，除此之外还可以 _自定义_ 一些用于页面运行中会用到的参数，如：发布模式(development or production)，API 地址(/api/github/com)等等。

## Meta 的使用方式

`<meta>` 的使用是通过 `name` 或者 `http-equiv`，组合 `content` 来使用的；

> 在没有定义 name 属性的时候，http-equiv 属性的值会作为 name 属性的值；
>
> 除此有一个特例：`charset`：是 HTML5 中的新属性，且替换了：`<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">`，但仍然允许使用 http-equiv 属性来规定字符集，但是使用新方法可以减少代码量

```html
<meta name="" content="" />
<!-- 或者 -->
<meta http-equiv="" content="" />
```

## Meta 分类

> meta 主要分为两大类:  
> ① name: 用于描述网页，比如网页的关键词，叙述等  
> ② http-equiv: equiv 全称是 `equivalent` 相等的意思，而 http-equiv 顾名思义，相当于 http 的头文件，用于告诉浏览器在加载页面时会用到的设置信息，如编码，是否缓存

### name 组

##### keywords

设置关键字，多个关键字英文逗号分隔

```html
<meta name="keywords" content="meta,github,html" />
```

##### description

页面描述信息

```html
<meta name="description" content="the meta you need to know. 150 letters limited" />
```

##### robots

设置搜索引擎哪些页面需要索引，哪些页面不需要索引

- all：文件将被检索，且页面上的链接可以被查询；
- none：文件将不被检索，且页面上的链接不可以被查询；
- index：文件将被检索；
- noindex：文件将不被检索，但页面上的链接可以被查询；
- follow：页面上的链接可以被查询；
- nofollow：文件将被检索，但页面上的链接不可以被查询

```html
<meta name="robots" content="index,nofollow" />

<meta name="robots" content="all" />
<!-- 等同 <meta name="robots" content="index,follow" /> -->

<meta name="robots" content="noindex,nofollow" />
<!-- 等同 <meta name="robots" content="nooindex,follow" /> -->

<!-- 还可以指定搜索引擎，如谷歌，百度 -->
<meta name="googlebot" content="all" />
<meta name="baiduspider" content="all" />
```

##### author

页面开发人

```html
<meta name="author" content="xing.he" />
```

##### generator

页面什么软件制作的

```html
<meta name="generator" content="worldpress" />
```

##### copyright

网站版权

```html
<meta name="copyright" content="gnotes" />
```

##### revisit-after

搜索引擎爬虫重访时间

```html
<meta name="revisit-after" content="7days" />
```

##### viewport

浏览器窗口的大小和缩放的

```html
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1" />
```

##### renderer

为双核浏览器准备的，用于指定双核浏览器默认以何种方式渲染页面

```html
<meta name="renderer" content="webkit" /><!--  默认webkit内核 -->
<meta name="renderer" content="ie-comp" />
<meta name="renderer" content="ie-stand" />
<meta name="renderer" content="webkit|ie-comp|ie-stand" />
```

##### google

告诉 Google 不提供此页面的翻译

```html
<meta name="google" content="notranslate" />
```

##### format-detection

禁用自动检测和格式化可能的电话号码

```html
<meta name="format-detection" content="telephone=no" />
```

### http-equiv 组

##### expires

设置网页的过期时间

```html
<meta http-equiv="expires" content="Fri May 13 2016 22:49:44 GMT+0800 (CST)" />
```

##### Pragma

禁止浏览器从本地缓存中访问页面，在 HTTP/1.0 中仅仅实现了 Pragma: no-cache

```html
<meta http-equiv="Pragma" content="no-cache" />
```

> `Pragma: no-cache` 跟 `Cache-Control: no-cache` 相同，Pragma: no-cache 兼容 http 1.0 ，Cache-Control: no-cache 是 http 1.1 提供的。  
> 因此，Pragma: no-cache 可以应用到 http 1.0 和 http 1.1；而 Cache-Control: no-cache 只能应用于 http 1.1

##### Refresh

自动刷新并跳转新页面，其中 content 第一个数字代表 5 秒后自动刷新

```html
<meta http-equiv="Refresh" content="5;URL=http://www.example.com" />
```

##### Set-Cookie

设置 Cookie

```html
<!-- 格式 -->
<meta http-equiv="Set-Cookie" content="name, date" />
<meta http-equiv="Set-Cookie" content="cookieName=cookieValue;expires=Friday,12-Jan-20100319:18:18GMT；path=/" />
```

> 如果网页过期。那么这个网页存在本地的 cookies 也会被自动删除

##### Window-target

强制页面在当前窗口以独立页面显示

```html
<meta http-equiv="Window-target" content="top" />
```

##### Content-Type

指定字符集，推荐使用 `charset`

```html
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
```

##### Content-Language

设置页面的语言

```html
<meta http-equiv="Content-Language" content="zh-cn" />
```

##### Cache-Control

设置页面缓存

```html
<meta http-equiv="Cache-Control" content="no-cache" />
```

> 可以不同的缓存机制，如：`max-age`、 `private`、 `no-cache`、 `must-revalidate`、 `no-store`

- `no-cache`: 先发送请求，与服务器确认该资源是否被更改，如果未被更改，则使用缓存。
- `no-store`: 不允许缓存，每次都要去服务器上，下载完整的响应。（安全措施）
- `public` : 缓存所有响应，但并非必须。因为 max-age 也可以做到相同效果
- `private` : 只为单个用户缓存，因此不允许任何中继进行缓存。（比如说 CDN 就不允许缓存 private 的响应）
- `max-age` : 表示当前请求开始，该响应在多久内能被缓存和重用，而不去服务器重新请求。例如：max-age=60 表示响应可以再缓存和重用 60 秒
- `must-revalidate` : 如果缓存的内容失效，请求必须发送到服务器/代理以进行重新验证存和重用 60 秒

##### Content-Script-Type

设置页面中脚本的类型

```html
<meta http-equiv="Content-Script-Type" content="text/javascript" />
```

##### x-dns-prefetch-control

通过设置为 "off" 完全退出 DNS 预取

```html
<meta http-equiv="x-dns-prefetch-control" content="off" />
```

### 移动端

```html
<meta name="apple-mobile-web-app-title" content="标题" />
<!-- 添加到主屏后的标题（iOS 6 新增） -->
<meta name="apple-mobile-web-app-capable" content="yes" />
<!-- 是否启用 WebApp 全屏模式，删除苹果默认的工具栏和菜单栏 -->

<meta name="apple-itunes-app" content="app-id=myAppStoreID, affiliate-data=myAffiliateData, app-argument=myURL" />
<!-- 添加智能 App 广告条 Smart App Banner（iOS 6+ Safari） -->
<meta name="apple-mobile-web-app-status-bar-style" content="black" />
<!-- 设置苹果工具栏颜色 -->
<meta name="format-detection" content="telphone=no, email=no" />
<!-- 忽略页面中的数字识别为电话，忽略email识别 -->

<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<!-- 针对手持设备优化，主要是针对一些老的不识别viewport的浏览器，比如黑莓 -->
<meta name="HandheldFriendly" content="true" />
<!-- 微软的老式浏览器 -->
<meta name="MobileOptimized" content="320" />
<!-- uc强制竖屏 -->
<meta name="screen-orientation" content="portrait" />
<!-- QQ强制竖屏 -->
<meta name="x5-orientation" content="portrait" />
<!-- UC强制全屏 -->
<meta name="full-screen" content="yes" />
<!-- QQ强制全屏 -->
<meta name="x5-fullscreen" content="true" />
<!-- UC应用模式 -->
<meta name="browsermode" content="application" />
<!-- QQ应用模式 -->
<meta name="x5-page-mode" content="app" />
<!-- windows phone 点击无高光 -->
<meta name="msapplication-tap-highlight" content="no" />

<meta name="application-name" content="应用名称" />
<!-- Web应用程序的名称(仅网站被用作一个应用时才使用它) -->

<meta name="skype_toolbar" content="skype_toolbar_parser_compatible" />
<!-- IE10: 禁用链接点击高亮 -->

<meta name="nightmode" content="disable" />
<!-- 在此页面禁用“夜间模式”（UC移动浏览器） -->

<meta name="layoutmode" content="fitscreen" />
<!-- 简化页面 减少数据传输（UC移动浏览器） -->
```

### 参考

- [一俢 | html meta](https://www.jianshu.com/p/6549bec5d0e1)
- [菜鸟 | Meta](https://www.runoob.com/tags/tag-meta.html)
- [chelen_jak | Html meta 标签汇总](https://blog.csdn.net/chelen_jak/article/details/19332857)
- [天满 | 关于 html 的 meta 标签总结](https://www.cnblogs.com/xiaoxiao666/p/6524489.html)
- [寒梁沐月 | html 头部 meta 标签汇总](https://www.jianshu.com/p/8d28e5130ab2)
- [SunSeekerX | HTML 常用 meta 大全](https://www.jb51.net/web/708299.html)
- [爱喝水的 qdy | Html 中 meta 标签汇总](https://blog.csdn.net/qq_32617703/article/details/103597964)
- [令狐寻欢 | HTML 中的 meta 标签常用属性及其作用总结](https://segmentfault.com/a/1190000010342600)
- [Haorooms | html 的 meta 总结，html 标签中 meta 属性使用介绍](https://www.haorooms.com/post/html_meta_ds)
- [芈洮科技 | HTMLmeta 标签总结](http://www.4006709770.com/dongtai/wzjs/46.html)
- [唯爱述虞谁 | HTML meta 标签总结与属性使用介绍](https://www.jianshu.com/p/cf62d11c046c)
