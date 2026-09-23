# 胜利会师 H5

以长征会师历程为主题的横屏交互 H5，包含地图叙事、诗朗诵、动态红绸与会师场景。

## 运行方式

项目使用 ES Modules 和本地素材，请通过静态 Web 服务器访问仓库根目录的 `index.html`。

发布到 GitHub Pages 后，入口即为仓库根目录。

## 嵌入其他 H5

页面会自动识别 iframe/浮窗环境，并提高 Canvas 像素密度、保持长版绸带参数、监听容器尺寸变化。宿主应直接把 iframe 设置为最终显示尺寸，避免用 `transform: scale()` 二次放大整个 iframe，否则 DOM 文字仍可能被浏览器栅格化后放大。

跨域宿主无法被页面自动测量时，可使用 `?embedScale=1.5` 指定外层缩放倍率；也可以响应页面发出的 `huishi:request-embed-scale` 消息，并向 iframe 回传：

```js
iframe.contentWindow.postMessage({
  type: 'huishi:embed-scale',
  scale: 1.5
}, '*');
```
