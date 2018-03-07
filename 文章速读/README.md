# 文章速读

### [主流浏览器内核介绍（前端开发值得了解的浏览器内核历史）](https://www.cnblogs.com/Leo_wl/p/5119719.html)
> 浏览器内核又可以分成两部分：渲染引擎(layout engineer 或者 Rendering Engine)和 JS 引擎。最开始渲染引擎和 JS 引擎并没有区分的很明确，后来 JS 引擎越来越独立，内核也就倾向于只指渲染引擎。常见的浏览器内核可以分这四种：Trident、Gecko、Blink、Webkit。
> 2008 之前，Apple 与 Google 旗下的浏览器内核都是 Webkit 。随后 2008 年谷歌公司发布 chrome 浏览器，采用的 chromium 内核便 fork 了 Webkit。2013 年 谷歌在 Chromium 项目中研发 Blink 渲染引擎,内置于 Chrome 浏览器之中。至此，两家公司在 浏览器内核方面分道扬镳。WebKit 由渲染引擎 "WebCore" 和 JS 解释引擎 "JSCore" 组成 ；在 Blink 中谷歌实际上认为 Webkit 中的 JSCore 不够好，才自己搞了一个 V8 JS 引擎，这就是 Chrome 比 Safari 在某些 JS 测试中效率更高的原因。
> 目前移动设备浏览器上常用的内核有 Webkit，Blink，Trident，Gecko 等，其中 iPhone 和 iPad 等苹果 iOS 平台主要是 WebKit，Android 4.4 之前的 Android 系统浏览器内核是 WebKit，Android4.4 系统浏览器切换到了Chromium，内核是 Webkit 的分支 Blink，Windows Phone 8 系统浏览器内核是 Trident。
