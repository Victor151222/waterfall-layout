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

## js实现与css3实现的比较

#### JavaScript原生方式

1. 需要计算，列数=浏览器窗口的宽度/图片宽度

   图片定位是根据每一列数据块的高度计算接下来图片的位置。

2. 图片排序是按照图片计算的位置横向排列，位置是计算出来的，比较规范。

#### css3方式

1. 不需要计算，浏览器自动计算，只需设置列宽，性能高（浏览器自动解析，不需要代码来计算）
2. 列宽随着浏览器窗口大小进行改变，用户体验不好
3. 图片排序按照垂直顺序排列，打乱图片显示顺序
4. 图片加载还是依赖JavaScript来实现的

***

转载自慕课网