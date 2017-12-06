title: Mobile
speaker: eyeseau
url: https://github.com/eyea/nodeppt
transition: zoomin
theme: moon
files: /js/demo.js,/css/demo.css,/js/zoom.js
highlightStyle: monokai_sublime
usemathjax: yes


<!-- 测试用 -->
[slide]
[移动端高清屏适配方案](http://www.zeakhold.com/231.html)







<!-- 封面 -->
[slide]
---
## 移动端*适配*的那些事儿
<small>*eyeseau*</small>

<!-- 首页 综述 -->
[slide]

# 话题的由来

[slide data-transition="vertical3d"]

## 关于适配想到了哪些
---
* 适配不仅仅是在页面布局 {:&.zoomin}
* PC端的适配(简单提及)
* 移动端的适配(布局及性能,但不仅限于移动端)

<!-- 几个概念 -->
[slide]

## 几个概念
----
* css像素 {:&.fadeIn}
* 物理像素
* 分辨率
* devicePixelRatio
* layout viewport
* visual viewport
* ideal viewport
> 关于这些概念可以在这里看到  https://github.com/riskers/blog/issues/17

[slide]
# css像素 {:&.flexbox.vleft}
* html中度量的单位 用px来计算，在pc中往往 css 1px ＝ 1 物理像素  {:&.fadeIn}<br>
* css像素在不同设备中1px对应不同的设备像素；iphone3分辨率是320*480 即 css 1px ＝ 1个物理像素；iphone4 分辨率640x960但屏幕尺寸没有改变，意味着同一块区域像素多了1倍 即 css 1px ＝2个物理像素
[slide]
# 物理像素 {:&.flexbox.vleft}
> 表示每英寸所拥有的像素数目，数值越高，代表屏幕能够以更高的密度来显示图像
[slide]
# 分辨率 {:&.flexbox.vleft}
> 显示器所能显示的像素多少，显示器可以显示的像素越多，画面就越精细，同样的屏幕区域能显示的信息就越多
[slide]
# devicePixelRatio
> window.devicePixelRadio = 物理像素/css像素 在iphone4中devicePixelRatio＝2 也就是1css像素＝2个物理像素
[slide]
# layout viewport
> 1.移动设备的默认viewport,css布局是以layout viewport 来做为参考系计算的; <br>
> 2.document.documenElement.clientWidth 获取
[slide]
# visual viewport
> 1.代表浏览器窗口的尺寸，当用户放大浏览器时这个尺寸就会变小; <br>
> 2.window.innerWidth 获取
[slide]
# ideal viewport
> 1.屏幕尺寸 设备屏幕的尺寸 单位是物理像素; <br>
> 2.screen.width 获取 屏幕尺寸是不变的; <br>
> 3.在该viewport中用户不需要缩放和横向滚动就可以正常查看网站的所有内容; <br>
> 4.设置移动端网站一般以这个viewport为准,ideal viewport 的宽度等于设备屏幕宽度，使得无论在什么分辨率下，那些针对ideal viewport设计的网站都可以完美的呈现给用户

<!-- PC 简要说明 -->
[slide data-transition="zoomin"]

## PC适配的简单说明
---
* 页面布局 {:&.zoomin}
  * 960px宽度的网格布局  {:&.zoomin}
  * 媒体查询+主体内容区定宽布局,达到某个节点之后隐藏某些元素(天猫、淘宝、微博)
  * 宽度和高度是js动态计算赋值(亚马逊)
  * [css布局原理](http://www.voidcn.com/article/p-cgnfbcnw-e.html) [PC端CSS布局汇总](http://www.voidcn.com/article/p-wvcrmohv-brb.html)
* 浏览器兼容性(IE、Safari、Chrome、Opera、Firefox...)
  * reset.css
  * [常见的浏览器兼容问题](http://www.jianshu.com/p/3521c6f11dd3?utm_campaign=maleskine&utm_content=note&utm_medium=seo_notes&utm_source=recommendation)

[note]
最开始是PC端网页，如果把移动端的可视区域(320-768)的话，大部分网站都会因为太窄而显示错乱；所以浏览器默认把viewport设置为一个较宽的值 980px或1024px，至少保证PC网站在移动端上可以显示，只不过出现了横向滚动条而已。
```javascript
<meta name="viewport" content="width=device-width">
```
meta viewport 中的通用属性：<br>
<span class="text-danger">width</span>
<span class="text-success">initial-scale</span>
<span class="text-warning">height</span><br>
<span class="text-primary">minimum-scale/maximum-scale</span><br>
<span class="text-info">user-scaleabel</span><br>
<span class="text-success">target-densitydpi</span><br>
<span class="text-primary">miniual-ui: ios的safari为meta表新增的属性，在网页加载是隐藏顶部的地址栏和底部的导航栏</span>

[/note]
<!-- 移动端适配开始 -->
[slide]

## 移动端的适配漫谈

[slide data-transition="glue"]
### 移动端适配 我们关注哪些问题呢？
---
* 布局(适配方案)  {:&.zoomin}
* 兼容(性能)



