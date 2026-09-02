# 备考资料

复习材料归档。本地入口是 `index.html`，双击即可，不需要联网。
线上（手机可看）：https://zhuojunji121-ctrl.github.io/exam-prep-notes/

## 目录约定

```
备考资料/
  index.html            # 索引页（唯一入口）
  vendor/               # 共用的前端库（echarts、中国省界 geojson），各条目引用 ../../vendor/
  <学科>/<条目名>/index.html
```

## 新增一份资料

1. 内容放到 `<学科>/<条目名>/index.html`，页面头部加一个 `← 返回索引` 链接指向 `../../index.html`。
2. 打开 `index.html`，在 `ENTRIES` 数组末尾追加一条：

```js
{ subject:'地理', title:'标题', desc:'一句话说明', path:'地理/条目名/index.html',
  date:'2026-09-02', tags:['标签'] }
```

学科分组、计数、排序都是自动的，不用改别的地方。

3. 发布到手机可见（GitHub Pages，仓库 `zhuojunji121-ctrl/exam-prep-notes`）：

```bash
cd ~/Desktop/备考资料 && git add -A && git commit -m "说明" && git push
```

推送后约 30 秒~1 分钟生效。仓库是公开的，但全站带 `noindex` + `robots.txt`，搜索引擎不收录。新页面记得也加 `<meta name="robots" content="noindex, nofollow">`。

## 手机适配

新页面统一带 `@media (max-width: 640px)` 分支：body padding 收到 12px、header 竖排、表格 `table-layout: fixed` + `word-break: break-word`（否则会横向溢出）。改完用 390px 宽的 iframe 验证 `scrollWidth === clientWidth`。

## 配色

沿用 dataviz skill 的参考色板（蓝 `#2a78d6` / 橙 `#eb6834`，深浅色两套 token），新条目直接复制现有页面的 `:root` 变量块。
