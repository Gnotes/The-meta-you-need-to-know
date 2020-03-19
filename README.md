# The-meta-you-need-to-know

> **Meta** 在 HTML 中大家都知道是用来描述页面信息的，但是具体有哪些呢？各自的使用方式及参数是什么呢，或许跟我现在一样 ~懵逼~

### 前言

在说 meta 之前我们先来了解下 `Metadata`，翻译过来是 **元数据**，是描述数据的数据(data about data)，用于描述数据属性（property）的信息，_在 HTML 中就是描述页面属性的一些描述信息_ [百度百科](https://baike.baidu.com/item/%E5%85%83%E6%95%B0%E6%8D%AE/1946090)

### Meta 能做些什么

Meta 常用于搜索引擎优化（SEO），定义页面编码语言(UTF-8)，页面缓存控制...(看完就明白了)，除此之外还可以 _自定义_ 一些用于页面运行中会用到的参数，如：发布模式(development or production)，API 地址(/api/github/com)等等。

### Meta 的使用方式

`<meta>` 的使用是通过 `name` 或者 `http-equiv`，组合 `content` 来使用的；

> 在没有定义 name 属性的时候，http-equiv 属性的值会作为 name 属性的值；
>
> 除此有一个特例：`charset`：是 HTML5 中的新属性，且替换了：`<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">`，但仍然允许使用 http-equiv 属性来规定字符集，但是使用新方法可以减少代码量

```html
<meta name="" content="" />
<!-- 或者 -->
<meta http-equiv="" content="" />
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
