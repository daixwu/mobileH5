# 移动端H5开发那些事儿

## 工具类网站

* [各种奇妙的hack](http://browserhacks.com/)
* [html5 移动端兼容性速查](http://mobilehtml5.org/)
* [css3 选择器测试](http://tools.css3.info/selectors-test/test.html)
* [各种各样的媒体查询收集](http://nmsdvid.com/snippets/)
* [css3 动画在线制作器](http://css3lib.alloyteam.com/#animation/AnimatedButtons)
* [css3 渐变在线制作器](http://www.colorzilla.com/gradient-editor/)
* [HTML5 Cross Browser Polyfills](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills)

## 框架

- [fullPage.js](https://github.com/powy1993/fullpage.git) 兼容桌面端(ie5.5+) 和 手机端
- [H5FullscreenPage.js](https://github.com/lvming6816077/H5FullscreenPage.git) 基于zepto全屏滚动
- [slip.js](https://github.com/binnng/slip.js.git) 移动端跟随手指滑动组件，零依赖
- [iSlider.js](https://github.com/kele527/iSlider.git) H5全屏滑动组件
- [zepto.fullpage.js](https://github.com/yanhaijing/zepto.fullpage.git) 可实现移动端的单页滚动效果，可自定义参数，提供回调接口，和公开接口。
- [touch.js](https://github.com/Clouda-team/touch.code.baidu.com.git) 百度移动设备上的手势识别与事件库
- [hammer.js](https://github.com/hammerjs/hammer.js.git) 一个多点触控手势的JavaScript库
- [quo.js](https://github.com/soyjavi/QuoJS.git) JavaScript手势库

## CSS重置

- [normalize.css](https://github.com/necolas/normalize.css.git)
- [HTML5 Reset](https://github.com/murtaugh/HTML5-Reset.git)
- [sanitize.css](https://github.com/10up/sanitize.css.git)
- [typo.css](https://github.com/sofish/typo.css.git) 一致化浏览器排版效果，构建最适合中文阅读的网页排版

## 动画库

- [animate.css](https://github.com/daneden/animate.css.git) 常用的css3动画库
- [magic.css](https://github.com/miniMAC/magic.git)
- [Effeckt.css](https://github.com/h5bp/Effeckt.css.git) 挺齐全的
- [动画工具](http://isux.tencent.com/css3/index.html) 腾讯ISUX 在线css3动画工具
- [parallax.js](https://github.com/wagerfield/parallax.git) 自适应智能设备方向的视差效果插件

## 加载动画

- [loaders.css](https://github.com/ConnorAtherton/loaders.css.git) 纯CSS加载动画
- <http://loading.io/> 在线 SVG / CSS / GIF

## 响应式工具

- [pageResponse.js](https://github.com/peunzhang/pageResponse.git) 使用transform:scale缩放页面
- [adaptive.js](https://github.com/finance-sh/adaptive.git) javascript H5自适应框架
- [hotcss.js](https://github.com/imochen/hotcss.git) 移动端布局开发解决方案

## 其他工具

- [prefixfree.js](https://github.com/LeaVerou/prefixfree.git) CSS3前缀补齐 [附带介绍](http://www.zhangxinxu.com/wordpress/?p=2035)
- [jquery.css3finalize.js](https://github.com/codler/jQuery-Css3-Finalize.git) CSS3前缀补齐
- [阿里巴巴矢量图标库](http://www.iconfont.cn/)

## study

- [滑屏 H5 开发实践九问](https://isux.tencent.com/nine-question-of-swipe-html5-page.html) 腾讯ISUX
- [CSS Animation性能优化](http://www.w3cplus.com/animation/animation-performance.html)

## 基础知识

meta标签，这些meta标签在开发webapp时起到非常重要的作用

```
<meta content="width=device-width; initial-scale=1.0; maximum-scale=1.0; user-scalable=0" name="viewport" />
<meta content="yes" name="apple-mobile-web-app-capable" />
<meta content="black" name="apple-mobile-web-app-status-bar-style" />
<meta content="telephone=no" name="format-detection" />
```

第一个meta标签表示：强制让文档的宽度与设备的宽度保持1:1，并且文档最大的宽度比例是1.0，且不允许用户点击屏幕放大浏览； 尤其要注意的是content里多个属性的设置一定要用分号+空格来隔开，如果不规范将不会起作用。

第二个meta标签是iphone设备中的safari私有meta标签，它表示：允许全屏模式浏览； 

第三个meta标签也是iphone的私有标签，它指定的iphone中safari顶端的状态条的样式； 

第四个meta标签表示：告诉设备忽略将页面中的数字识别为电话号码



## 适配类文章

[移动端高清、多屏适配方案](http://www.html-js.com/article/Mobile-terminal-H5-mobile-terminal-HD-multi-screen-adaptation-scheme%203041)

[手机淘宝的flexible设计与实现](http://www.html-js.com/article/2402)

### 去掉被触摸时产生的半透明灰色遮罩

```css
-webkit-tap-highlight-color: rgba(0,0,0,0);
-webkit-tap-highlight-color: transparent;
```

### 使iphone或ipad div 滑动效果顺畅

```css
body {
	-webkit-overflow-scrolling: touch;
}
```

### 字体清晰

```css
-webkit-font-smoothing: antialiased; 
```

### placeholder--line-height

input 的placeholder会出现文本位置偏上的情况：PC端设置line-height等于height能够对齐，而移动端仍然是偏上，解决是设置line-height：normal。

### 消除transition闪屏

两个方法：使用css3动画的时尽量利用3D加速，从而使得动画变得流畅。动画过程中的动画闪白可以通过 backface-visibility 隐藏。

```css
-webkit-transform-style: preserve-3d;
/*设置内嵌的元素在 3D 空间如何呈现：保留 3D*/
-webkit-backface-visibility: hidden;
/*（设置进行转换的元素的背面在面对用户时是否可见：隐藏）*/
```

### 禁止ios 长按时不触发系统的菜单，禁止ios&android长按时下载图片

```css
-webkit-touch-callout:none
```

### 禁止ios和android用户选中文字

```css
-webkit-user-select:none
```

### 禁止长按链接与图片弹出菜单

```css
a,img { -webkit-touch-callout: none }    
```

### 禁止ios和android用户选中文字

```css
html,body {-webkit-user-select:none; user-select: none; }
```

### 改变输入框placeholder的颜色值

```css
::-webkit-input-placeholder { /* WebKit browsers */
color: #999; }
:-moz-placeholder { /* Mozilla Firefox 4 to 18 */
color: #999; }
::-moz-placeholder { /* Mozilla Firefox 19+ */
color: #999; }
:-ms-input-placeholder { /* Internet Explorer 10+ */
color: #999; }
input:focus::-webkit-input-placeholder{ color:#999; }
```

### android上去掉语音输入按钮

```css
input::-webkit-input-speech-button {display: none}
```

### 取消input在ios下，输入的时候英文首字母的默认大写

```html
<input autocapitalize="off" autocorrect="off" />
```

### 手机拍照和上传图片

IOS有拍照、录像、选取本地图片功能，部分Android只有选择本地图片功能。Winphone不支持

```html
<input type="file" accept="images/*" />
<input type="file" accept="video/*" />
```

### 屏幕旋转的事件和样式

```js
//JS处理
function orientInit(){
	var orientChk = document.documentElement.clientWidth > document.documentElement.clientHeight?'landscape':'portrait';
	if(orientChk =='lapdscape'){
		//这里是横屏下需要执行的事件
	}else{
		//这里是竖屏下需要执行的事件
	}
}

orientInit();
window.addEventListener('onorientationchange' in window?'orientationchange':'resize', function(){
	setTimeout(orientInit, 100);
},false)	

//CSS处理
//竖屏时样式
@media all and (orientation:portrait){   }
//横屏时样式
@media all and (orientation:landscape){   }
```

### 重力感应事件

```js
// 运用HTML5的deviceMotion，调用重力感应事件
if(window.DeviceMotionEvent){
	document.addEventListener('devicemotion', deviceMotionHandler, false)
}	

var speed = 30;
var x = y = z = lastX = lastY = lastZ = 0;
function deviceMotionHandler(eventData){
	var acceleration = event.accelerationIncludingGravity;
	x = acceleration.x;
	y = acceleration.y; 
	z = acceleration.z;
	if(Math.abs(x-lastX)>speed || Math.abs(y-lastY)>speed || Math.abs(z-lastZ)>speed ){
		//这里是摇动后要执行的方法 
		yaoAfter();
	}
	lastX = x;
	lastY = y;
	lastZ = z;
}

function yaoAfter(){
	//do something
}
```

### 关于定位的坑

**fixed定位**

1. ios下fixed元素容易定位出错，软键盘弹出时，影响fixed元素定位
2. android下fixed表现要比iOS更好，软键盘弹出时，不会影响fixed元素定位
3. ios4下不支持position:fixed

解决方案：使用 [Iscroll](http://cubiq.org/iscroll-5) ，如：

```html
<div id="wrapper">
    <ul>
        <li></li>
        .....
    </ul>
</div>
<script src="iscroll.js"></script>
<script>
	var myscroll;
	function loaded(){
		myscroll=new iScroll("wrapper");
	}
	window.addEventListener("DOMContentLoaded",loaded,false);
</script>
```

**position定位**
Android下弹出软键盘弹出时，影响absolute元素定位
解决方案:

```js
var ua = navigator.userAgent.indexOf('Android');

if(ua>-1){

	$('.ipt').on('focus', function(){

		$('.css').css({'visibility':'hidden'})

	}).on('blur', function(){

		$('.css').css({'visibility':'visible'})

	})

}
```

### 播放视频不全屏

1. ios7+支持自动播放

2. 支持Airplay的设备（如：音箱、Apple TV)播放 `x-webkit-airplay="true"` 

3. 播放视频不全屏 `webkit-playsinline="true"` 

```html
<video x-webkit-airplay="true" webkit-playsinline="true" preload="auto" autoplay src="http://"></video>
```

[html5--移动端视频video的android兼容，去除播放控件、全屏等](https://www.jianshu.com/p/4118510f3205?utm_campaign=maleskine&utm_content=note&utm_medium=seo_notes&utm_source=recommendation)

[移动端实践 - video](https://www.jianshu.com/p/a6a1113a1597)

### JS判断设备

```js
function deviceType(){
	var ua = navigator.userAgent;
	var agent = ["Android", "iPhone", "SymbianOS", "Windows Phone", "iPad", "iPod"];	
	for(var i=0; i<len,len = agent.length; i++){
		if(ua.indexOf(agent[i])>0){			
			break;
		}
	}
}
deviceType();
window.addEventListener('resize', function(){
	deviceType();
})
```

### JS判断微信浏览器

```js
function isWeixin(){
	var ua = navigator.userAgent.toLowerCase();
	if(ua.match(/MicroMessenger/i)=='micromessenger'){
		return true;
	}else{
		return false;
	}
}
```

### android 2.3 bug

1. @-webkit-keyframes 需要以0%开始100%结束，0%的百分号不能去掉
2. after和before伪类无法使用动画animation
3. border-radius不支持%单位，如要兼容，可以给radius设置一下较大的值
4. translate百分比的写法和scale在一起会导致失效，例如：`-webkit-transform: translate(-50%,-50%) scale(-0.5, 1)`

### android 4.x bug

1. 三星 Galaxy S4中自带浏览器不支持border-radius缩写
2. 同时设置border-radius和背景色的时候，背景色会溢出到圆角以外部分
3. 部分手机(如三星)，a链接支持鼠标:visited事件，也就是说链接访问后文字变为紫色
4. android无法同时播放多音频audio

### 消除transition闪屏

```
.css {
	-webkit-transform-style: preserve-3d;
	-webkit-backface-visibility: hidden;
	-webkit-perspective: 1000;
}
```

### 开启硬件加速

目前，像Chrome/Filefox/Safari/IE9+以及最新版本Opera都支持硬件加速，当检测到某个DOM元素应用了某些CSS规则时就会自动开启，从而解决页面闪白，保证动画流畅。

```
.css {
	-webkit-transform: translate3d(0,0,0);
	-moz-transform: translate3d(0,0,0);
	-ms-transform: translate3d(0,0,0);
	transform: translate3d(0,0,0);
}
```

### 渲染优化

1. 禁止使用iframe（阻塞父文档onload事件）
2. 禁止使用gif图片实现loading效果（降低CPU消耗，提升渲染性能）
3. 使用CSS3代码代替JS动画；
4. 开启GPU加速；
5. 使用base64位编码图片

对于一些小图标，可以使用base64位编码，以减少网络请求。但不建议大图使用，比较耗费CPU。小图标优势在于：

1. 减少HTTP请求；
2. 避免文件跨域；
3. 修改及时生效；

### 媒体查询常用样式表：

```
<link rel="stylesheet" media="all and (orientation:portrait)" href="portrait.css">    // 竖放加载
<link rel="stylesheet" media="all and (orientation:landscape)"href="landscape.css">   // 横放加载

//竖屏时使用的样式
<style media="all and (orientation:portrait)" type="text/css">
	#landscape { display: none; }
</style>

//横屏时使用的样式
<style media="all and (orientation:landscape)" type="text/css">
	#portrait { display: none; }
</style>
```

### [关于zepto需要注意的地方](https://www.cnblogs.com/yddlvo/p/8041286.html)

zepto中本没有长按事件，如果需要，需这样写： 

```js
$.fn.longPress = function(fn) {
    var timeout = undefined;
    var $this = this;
    for(var i = 0;i<$this.length;i++){
        $this[i].addEventListener('touchstart', function(event) {
            timeout = setTimeout(fn, 1000);  //长按时间超过1000ms，则执行传入的方法
            }, false);
        $this[i].addEventListener('touchend', function(event) {
            clearTimeout(timeout);  //长按时间少于800ms，不会执行传入的方法
            }, false);
    }
}

$(选择器).longPress (fn)
```

注意：

在这种场景中（长按验票）：按下的同时，进度条开始跑起来（动画）,动画跑完时，才能调用接口,否则，动画回到起始点。代码如下:

```js
$.fn.longPress = function(fn1,fn2) {
    var $this = this;
    var timeout = undefined;
    for(var i = 0;i<$this.length;i++){
        $this[i].addEventListener('touchstart', function(event) {
            timeout = new Date().getTime();
            fn1();
            event.preventDefault();
        }, false);
            
        $this[i].addEventListener('touchend', function(event) {
            if(new Date().getTime()-timeout<1500){
                fn2(new Date().getTime()-timeout);
            }
            event.preventDefault();   
        }, false);
            
    }
}
$('.checkDiv').longPress(function(){    
    $('#progressDiv').stop().animate({width:'100%'},1500,function(){
        console.log('调用接口')
    })
},function(time){
    if($('#progressDiv')[0].style.width == '100%'){
        return;
    }
    $('#progressDiv').stop().animate({width:'0px'},time,function(){})
})
```

