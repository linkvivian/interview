# Web优化

## **网络角度**

- 合并JS脚本和CSS样式表
- 将图片嵌入CSS代码（data:mediatype; base64,data），使用CSS sprite
- 静态文件采用 cdn 引入
- 合理使用HTTP的缓存头，利用缓存。
- 对于代码应该考虑性能来编写,比如使用`requestAnimationFrame`绘制动画,尽可能减少页面重绘(DOM 改变)
- `Webpack`打包时分离第三方依赖的chunk`vendor`，异步加载`chunk`，加快首屏渲染，减少打包整体体积
- 域名分区
- 页面做服务端渲染，优化seo，减少客户端处理时间



## **浏览器和页面渲染的角度**

- HTML文档结构层次尽量少，最好不深于六层
- JS脚本尽量后放
- 少量首屏样式内联放在标签内
- 样式结构层次尽量简单
- 在脚本中尽量减少DOM操作，尽量缓存访问DOM的样式信息，避免过度触发回流
- 减少通过JavaScript代码修改元素样式，尽量使用修改class名方式操作样式或动画
- 动画尽量使用在绝对定位（absolute）或固定（fixed）定位的元素上
- 隐藏在屏幕外，或在页面滚动时，尽量停止动画
- 尽量缓存DOM查找，查找器尽量简洁
- 涉及多域名的网站，可以开启域名预解析，使用`<link rel='dns-prefetch' />`


## 雅虎优化军规

- 减少HTTP请求
- 减少DNS查询
- 避免跳转
- 让Ajax可缓存
- 延迟加载组件
- 预加载组件
- 减少DOM元素
- 域名分区，注意DNS查询的副作用（最好2-4个）
- 尽量不使用`iframe`
- 不要 404（浪费HTTP请求)
- 使用 CDN
  - CDN是一群不同地点的服务器，可以更高效地分发内容到用户
- 使用 HTTP 缓存
- 利用 Gzip 压缩
  - html，脚本，样式，xml 和 json 等等都应该被 gzip，而图片，pdf 等等不应该被 gzip
- 减少cookie的大小
- 保证静态组件的请求是没有cookie的。可以创建一个子域名来托管所有静态组件
- 把CSS样式放在顶部。
- 把JS放底部
- 使用外部JS和CSS。可以利用缓存
- 压缩JS和CSS。
- 最小化DOM访问。
- 事件委托