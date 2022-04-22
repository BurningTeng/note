### ::after
CSS伪元素::after用来创建一个伪元素，作为已选中元素的最后一个子元素。通常会配合content属性来为该元素添加装饰内容。这个虚拟元素默认是行内元素。
### @media
@media 规则在媒体查询中用于为不同的媒体类型/设备应用不同的样式。  
如果浏览器窗口的宽度为 600px 或更小时，把 <body> 元素的背景颜色更改为“浅蓝色”：
```css
@media only screen and (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
``` 