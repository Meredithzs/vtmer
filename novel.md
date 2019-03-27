# 3.23笔记
### letter-spacing 属性
- 设置字与字之间的宽度
### word-spacing 属性
- 词与词之间的宽度
# 3.24笔记
### 搜索栏的创建
- 简书式
![搜索栏1](F:/图片/笔记/1.png)
> html
```
<div class="container">
    <form action="" class="parent">
        <input type="text" class="search"  placeholder="搜索"> <!搜索栏的建立>
        <input type="button" name="" id="" class="btn">
    </form>
</div>
```
> css 
``` * {
    margin: 0;
    padding: 0;
}
.container {
    height: 70px;
    width: 800px;
    margin: 100px auto 0 auto;
}
.parent {
    position: relative;
}
.search {
    width: 300px;
    height: 40px;
    border-radius: 18px;
    outline: none;
    border: 1px solid #ccc;
    padding-left: 20px;
    position: absolute;
}
.btn {
    height: 35px;
    width: 35px;
    position: absolute;
    background: url("images/topbar.png") no-repeat -2px -99px;
    top: 6px;
    left: 285px;
    border: none;
    outline: none;
    cursor: pointer;
}
```
- 百度类
![搜索栏2](![image](F:/%E5%9B%BE%E7%89%87/%E7%AC%94%E8%AE%B0/5.png))
# 3.27笔记
### flex布局
> ### flex布局是什么？
- 弹性布局，为盒状模型提供最大的灵活性
- 任一容器都可以指定为flex布局

```
.box {
    display: flex;
}
```
- 行内元素也可以使用flex布局
```
.box {
    display:inline-flex;
}
```
**==设为flex布局以后，子元素的float、clear和vertical-align属性将失效==**
> ### 基本概念
- 采用flex布局的元素 称为flex容器 其所有子元素自动称为容器成员 称为flex项目
- 容器默认存在两根轴
   - 水平主轴 
   - 垂直交叉轴
- 项目默认沿主轴排列
- 单个项目占据主轴空间叫做main size
  占据的交叉轴空间叫做cross size
> ### 容器的属性
- flex-direction
   - 决定主轴方向（即项目的排列方向）
   - row（默认值）：主轴为水平方向，起点在左端。
   - row-reverse：主轴为水平方向，起点在右端。
   - column：主轴为垂直方向，起点在上沿。
   - column-reverse：主轴为垂直方向，起点在下沿。
   
![image](F:/%E5%9B%BE%E7%89%87/%E7%AC%94%E8%AE%B0/4.png)
```
.box {
  flex-direction: row | row-reverse | column | column-reverse;
}
```
- flex-wrap
   - nowrap（默认）：不换行
   - wrap：换行，第一行在上方
   - wrap-reverse：换行，第一行在下方
- **flex-flow**:   flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap
- **justify-content**
   - 定义了项目在主轴上的对齐方式
   - flex-start（默认值）：左对齐
   - flex-end：右对齐
   - center： 居中
   - space-between：两端对齐，项目之间的间隔都相等。
   - space-around：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。
 ![image](F:/%E5%9B%BE%E7%89%87/%E7%AC%94%E8%AE%B0/5.png)
- **align-items**  
   - 定义项目在交叉轴上如何对齐
   - flex-start：交叉轴的起点对齐
   - flex-end：交叉轴的终点对齐。
   - center：交叉轴的中点对齐。
   - baseline: 项目的第一行文字的基线对齐。
   - stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。
 ![image](F:/图片/笔记/6.png)
- align-content
   - 定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用
   - flex-start：与交叉轴的起点对齐
   - flex-end：与交叉轴的终点对齐
   - center：与交叉轴的中点对齐。
   - space-between：与交叉轴两端对齐，轴线之间的间隔平均分布。
   - space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
   - stretch（默认值）：轴线占满整个交叉轴。
 ![image](F:/图片/笔记/7.png)
> ### 项目属性
- order
   - 定义项目的排列顺序。
   - 数值越小，排列越靠前，默认为0。
- flex-grow
   - 定义项目的放大比例
   - 默认为0，即如果存在剩余空间，也不放大
- flex-shrink
   - 定义了项目的缩小比例
   - 默认为1，即如果空间不足，该项目将缩小
- flex-basis
   - 定义了在分配多余空间之前，项目占据的主轴空间（main size）。
   - 浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。
   - 它可以设为跟width或height属性一样的值（比如350px），则项目将占据固定空间。
- flex
- align-self
   - 允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。
   - 默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。
> ### 骰子布局
 实例[：骰子布局](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html/)

