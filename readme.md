## Flexbox布局练习例子

#### 参考资源

>> Flex 布局教程：语法篇 ： http://www.ruanyifeng.com/blog/2015/07/flex-grammar.htmlFlex

布局教程：实例篇 ：http://www.ruanyifeng.com/blog/2015/07/flex-examples.html

Flex 布局教程：实例篇 (代码) ：https://codepen.io/LandonSchropp/pen/KpzzGo​

​Flex 布局练习示例代码：https://github.com/XK-one/FlexboxTest​

### Flex布局的简介

Flex 是 Flexible Box 的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性任何一个容器都可以指定为 Flex 布局，行内元素也可以使用 Flex 布局，Webkit 内核的浏览器，必须加上-webkit前缀，即 display: -webkit-flex; /* Safari */​注意，设为 Flex 布局以后，子元素的float、clear和vertical-align属性将失效
​
### 基本概念

容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做main start，结束位置叫做main end；交叉轴的开始位置叫做cross start，结束位置叫做cross end。项目默认沿主轴排列。单个项目占据的主轴空间叫做main size，占据的交叉轴空间叫做cross size
flex作用的容易默认存在两根轴，水平的主轴和垂直的交叉轴，项目(子控件)默认沿主轴从左到右排列,

### 容器的属性

**flex-direction**

flex-direction属性决定主轴的方向, 即项目(子控件)的排列方向有4个取值： 
	
 - ​​row（默认值）：主轴为水平方向，起点在左端，自左向右 
 - ​row-reverse：主轴为水平方向，起点在右端，自右向左 
 - column：主轴为垂直方向，起点在上沿，自上而下 
 - column-reverse：主轴为垂直方向，起点在下沿，从下到上

**flex-wrap**

默认情况下，项目都排在一条线（又称"轴线"）上。flex-wrap属性定义，如果一条轴线排不下，如何换行即 flex-wrap 属性用来指明子控件怎样换行. 至于换行的方式看下面取值​​ 

 - ​nowrap（默认）：不换行 
 - wrap：换行，第一行在上方 
 - wrap-reverse：换行，第一行在下方， 第二行在上方，从下到上~一行一行排列

**flex-flow**

flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap

**justify-content**

justify-content属性定义了项目在主轴上的对齐方式可能取5个值，具体对齐方式与轴的方向有关。下面假设主轴为从左到右​​​​ 

 - flex-start（默认值）：左对齐​​ 
 - flex-end：右对齐​​ - ​ center： 居中​ ​​
 - space-between：两端对齐，项目(控件)之间的间隔都相等​​ 
 - space-around：每个项目(控件)两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍

> 注意：这里的取值要结合flex-direction，对齐方式是和主轴的方向有关的

​​
**align-items**

align-items属性定义项目在交叉轴上如何对齐可能取5个值。具体的对齐方式与交叉轴的方向有关，下面假设交叉轴从上到下​​​​​ 

 - flex-start：交叉轴的起点对齐​​​ 
 - flex-end：交叉轴的终点对齐​​​ 
 - center：交叉轴的中点对齐​​​ 
 - baseline: 项目的第一行文字的基线对齐​​​ 
 - ​​​​stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度


**align-content**

align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用该属性可能取6个值:​​​​​ 

 - ​​flex-start：与交叉轴的起点对齐​​​​​ 
 - flex-end：与交叉轴的终点对齐​​​​​ 
 - center：与交叉轴的中点对齐​​​​​ 
 - space-between：与交叉轴两端对齐，轴线之间的间隔平均分布​​​​​ 
 - space-around：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍​​​​​ 
 - stretch（默认值）：轴线占满整个交叉轴


### 项目(控件)的属性

**order**

> order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0


**flex-grow**

> flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍

​
**flex-shrink**

> flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小如果所有项目的flex-shrink属性都为1，当空间不足时，都将等比例缩小。如果一个项目的flex-shrink属性为0，其他项目都为1，则空间不足时，前者不缩小负值对该属性无效

​​
**flex-basis**

>flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小它可以设为跟width或height属性一样的值（比如350px），则项目将占据固定空间
​
**flex**

>flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)。建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值

​
**align-self**

>align-self属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch该属性可能取6个值，除了auto，其他都与align-items属性完全一致​​注意： align-self的场景是作用在项目(控件)上, 当单个项目有与其他项目不一样的对齐方式，这时候align-self就能上场了​​​​