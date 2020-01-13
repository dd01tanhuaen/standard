# 移动端开发细节

## WebApp Meta 标签设置(iOS)

一. Viewport Meta Tag

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0,
maximum-scale=1.0, user-scalable=no">
```

  * width – viewport的宽度

  * height – viewport的高度

  * initial-scale – 初始的缩放比例

  * minimum-scale – 允许用户缩放到的最小比例

  * maximum-scale – 允许用户缩放到的最大比例

  * user-scalable – 是否允许用户缩放



二. apple-mobile-web-app-capable: 设置 WebApp 是否进入全屏模式，该设置需要添加到主屏幕才生效

  ```html
    <meta name="apple-mobile-web-app-capable" content="yes">
  ```

  * content设置 yes 进入全屏模式
  * 默认会启动 Safari 应用，使用 Safari 应用浏览
  * 通过检测 window.navigator.standalone 的 Boolean 值可以判断 web 应用是否处于全屏模式

三. apple-mobile-web-app-status-bar-style: 状态栏的设置

  ```html
  <meta name="apple-mobile-web-app-status-bar-style" content="black">
  ```

  * 此 meta 设置只在全屏模式生效
  * 默认值是 default
  * content=”black”，状态栏背景黑色，网页内容在状态栏下面
  * content=”black-translucent”，状态栏半透明，背景黑色，网页内容占满全屏

