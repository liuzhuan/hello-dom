# 节点几何尺寸

## offsetTop & offsetLeft

`offsetTop` 和 `offsetLeft` 指定了元素相对于其 `offsetParent` 的距离，以像素为单位。

`offsetParent` 是指距离元素最近，且 `position` 不等于 `static` 的父级元素。如果没有寻得此类元素，则 `<body>` 将作为 `offsetParent`。

如果搜寻过程中发现 `<td>`, `<tr>` 或 `<table>` 元素，即使它们的 `position` 是 `static`，也可以作为 `offsetParent`。

```js
div.offsetLeft		// 60
div.offsetTop		// 60
div.offsetParent	// <body>
```

## getBoundingClientRect()

获取元素相对于视图的 `top`, `right`, `bottom` 及 `left` 边距偏移量。`top` 和 `bottom` 均返回相对于视图顶部的垂直距离，`left` 和 `right` 均返回相对于视图左侧的水平距离。

```js
var rect = el.getBoundingClientRect();
rect.top,		// 100
rect.right,		// 170
rect.bottom,	// 170
rect.left,		// 100
```

返回的 width 和 height，包含内外边距和边框，即 `border + padding + content`

```js
rect.width,		// 125
rect.height,		// 125
```

## offsetWidth & offsetHeight

`offsetWidth` 和 `offsetHeight` 返回值和 `getBoundingClientRect()` 得到的尺寸相同，即包含内外边距和边框。

```js
el.offsetWidth	// 125
el.offsetHeight	// 125
```

## clientWidth & clientHeight

`clientWidth` 和 `clientHeight` 得到的尺寸包含内边距和内容，不包含边框，即 `content + padding`

```js
el.clientWidth		// 75
el.clientHeight	// 75
```

## elementFromPoint()

获取某个位置点下最上层的元素。位置点坐标相对于视窗。

```js
document.elementFromPoint(50, 50)	// <div id="top"></div>
```

## scrollWidth & scrollHeight

获取滚动元素的尺寸。

```js
el.scrollHeight	    // 1000
el.scrollWidth		// 1000
```

## scrollTop & scrollLeft

用来获取或者设定滚动距离，两者均可读可写。

```js
el.scrollTop = 750
el.scrollLeft = 750
el.scrollTop 			// 750
el.scrollLeft			// 750
```

## scrollIntoView()

将元素滚动入视窗

```js
el.scrollIntoView(true);
```

## REF

- [DOM Enlightenment - Chapter 5 - Element Node Geometry & Scrolling Geometry](http://www.domenlightenment.com/#5)