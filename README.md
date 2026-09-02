# 备考资料

复习材料归档。入口是 `index.html`，双击即可，不需要联网、不需要起服务。

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

## 配色

沿用 dataviz skill 的参考色板（蓝 `#2a78d6` / 橙 `#eb6834`，深浅色两套 token），新条目直接复制现有页面的 `:root` 变量块。
