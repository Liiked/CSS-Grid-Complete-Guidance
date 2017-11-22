# CSS-Grid-Complete-Guidance

> css 网格布局完全指南，[查看翻译原文地址](https://css-tricks.com/snippets/css/complete-guide-grid/)
>
> - 参考：
>   - [CSS GRID LEVEL1 from W3C](https://www.w3.org/TR/css-grid-1)
>   - [CSS Grid Layout from MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Grid_Layout)
 - [基础](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E5%9F%BA%E7%A1%80.md)
- [教程（1）网格容器](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/教程(1)网格容器.md)

- [教程（2）网格项](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/教程(2)网格项.md)
- 难点和重点
    - [不可见网格(隐式网格)](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-auto-columns--grid-auto-rows)
    - [`fr`单位](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-template-columns--grid-template-rows)
    - [`column, float, clear, vertical-align`等属性在网格中不产生效果](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#display)
    - [网格间隙不等同于`margin, padding`](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-column-gap--grid-row-gap)
    - justify-水平对齐，align-垂直对齐

## 术语表
- **网格布局**（Grid）：由*网格容器*和*网格项*组合而成的现代CSS布局形式。
- **网格容器**（Grid Container）：设置`display:grid`的元素，所有*网格项*（Grid Items）的直属父级元素。网格容器中的子元素也可以为网格容器——嵌套网格布局。
- **网格项**（Grid Items）：*网格容器*的直接子元素（直属后代元素），一旦直属父元素设置为`grid`布局，那么这个父元素的子元素自动为*网格项*。
- **网格分隔线**（Grid Items）：组成网格基本结构的分隔线。*分隔线*可以是垂直的（列分隔线），也可以是水平的（行分隔线）。
- **网格单元**（Grid Items）：由两个相邻*行分隔线*和*列分隔线*交汇出的区域。当执行网格项定位的时候，网格项引用的最小网格单位（注：网格布局中的逻辑概念，实际中并不使用）。
- **网格轨道**（Grid Items）：*网格单元*的一种逻辑布局形式，表示网格中的一*行*或者一*列*，其前身是Grid Column和Grid row。
- **网格区域**（Grid Items）：*网格单元*的一种逻辑布局形式，指定*网格分隔线*包围起来的区域，包含一个或多个连续相邻的网格单元。

## 网格属性表

> 这里给出的是css属性表，不是值，不要搞错了。
### 网格容器（Grid Container）
- [display](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#display)
- [grid](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid)
- [grid-template-columns](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-template-columns--grid-template-rows)
- [grid-template-rows](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-template-columns--grid-template-rows)
- [grid-template-areas](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-template-areas)
- [grid-template](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-template)
- [grid-column-gap](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-column-gap--grid-row-gap)
- [grid-row-gap](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-column-gap--grid-row-gap)
- [grid-gap](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-gap)
- [grid-auto-columns](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-auto-columns--grid-auto-rows)
- [grid-auto-rows](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-auto-columns--grid-auto-rows)
- [grid-auto-flow](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-auto-flow)
- [justify-items](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#justify-items)
- [justify-content](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#justify-content)
- [align-items](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#align-items)
- [align-content](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#align-content)
### 网格项（Grid Items）
- [grid-column-start](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(2)%E7%BD%91%E6%A0%BC%E9%A1%B9.md#grid-column-start--grid-column-end-grid-row-start--grid-row-end)
- [grid-column-end](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(2)%E7%BD%91%E6%A0%BC%E9%A1%B9.md#grid-column-start--grid-column-end-grid-row-start--grid-row-end)
- [grid-row-start](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(2)%E7%BD%91%E6%A0%BC%E9%A1%B9.md#grid-column-start--grid-column-end-grid-row-start--grid-row-end)
- [grid-row-end](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(2)%E7%BD%91%E6%A0%BC%E9%A1%B9.md#grid-column-start--grid-column-end-grid-row-start--grid-row-end)
- [grid-column](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(2)%E7%BD%91%E6%A0%BC%E9%A1%B9.md#grid-column)
- [grid-row](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(2)%E7%BD%91%E6%A0%BC%E9%A1%B9.md#grid-row)
- [grid-area](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(2)%E7%BD%91%E6%A0%BC%E9%A1%B9.md#grid-area)
- [justify-self](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(2)%E7%BD%91%E6%A0%BC%E9%A1%B9.md#justify-self)
- [align-self](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(2)%E7%BD%91%E6%A0%BC%E9%A1%B9.md#align-self)