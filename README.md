# JavaScript版本

```html
<div class="pin">
    <div class="box">
        <img src="./images/1.jpg"/>
    </div>
</div>
```
pin盒子用来控制盒子直接的间距；box盒子用来控制盒子的样式



```css
.pin{
    padding: 15px 0 0 15px;
    float:left;
}
.box{
    padding: 10px;
    border:1px solid #ccc;
    box-shadow: 0 0 6px #ccc;
    border-radius: 5px;
}
.box img{
    width:162px;
    height:auto;
}
```
offsetWidth = 199

宽度199 = 图片宽度162 + 内边距10X2 + 边框宽度1X2 + 15



因为offsetWidth只能获取到包括padding在内的高度，不能获取到margin的宽度，为了方便所以这里用padding来控制pin盒子的边距



#### js实现原理

1. 先初始化加载一部分图片，当滚动条滚动到一定程度的时候，加载从后台返回的json数据里面的图片资源。
2. 先加载一列图片，后续往第一列图片中高度最低的图片后面添加下一张图片，同时更新列里面的各列高度。重复往每列中高度最小的图片后面添加下一张。