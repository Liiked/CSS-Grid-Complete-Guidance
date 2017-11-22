<link href="http://kevinburke.bitbucket.org/markdowncss/markdown.css" rel="stylesheet"></link>

# CSS-Grid-Complete-Guidance
> css 网格布局完全指南，[查看翻译原文地址](https://css-tricks.com/snippets/css/complete-guide-grid/)

 - [基础](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E5%9F%BA%E7%A1%80.md)
- [教程（1）网格容器](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/教程(1)网格容器.md)

- [教程（2）网格项](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/教程(2)网格项.md)
- 难点和重点
    - [不可见网格(隐式网格)](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-auto-columns--grid-auto-rows)
    - [`fr`单位](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-template-columns--grid-template-rows)
    - [`column, float, clear, vertical-align`等属性在网格中不产生效果](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#display)
    - [网格间隙不等同于`margin, padding`](https://github.com/Liiked/CSS-Grid-Complete-Guidance/blob/master/%E6%95%99%E7%A8%8B(1)%E7%BD%91%E6%A0%BC%E5%AE%B9%E5%99%A8.md#grid-column-gap--grid-row-gap)
    - justify-水平对齐，align-垂直对齐

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