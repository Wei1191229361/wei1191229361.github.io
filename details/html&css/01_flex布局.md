## Flex布局分析
> &emsp;&emsp;最近移动端布局常用到Flex布局,发现不太熟悉,做个整理,只介绍一下常用的属性
### 一、Flex布局
&emsp;&emsp;Flex布局意为"弹性盒布局。传统的布局方式中，块级布局更侧重于垂直方向、行内布局更侧重于水平方向。弹性盒子布局则与方向无关。<br/>

&emsp;&emsp;所谓弹性盒布局意思就是在弹性容器(flex container)中,弹性项目(Flex item)可以在沿垂直或者水平方向排列(由flex-direction确定)，并且可以按比例伸缩；
### 二、如何使用flex布局
&emsp;&emsp;通过将一个容器display的值设置为flex，这个容器就会变成一个**弹性容器**，即flex container。<br/>它内部的元素就会自动变为**弹性项目**，即flex item；

![](01_flex布局_images\\flex-container.png)

 如图中所示，主轴方向由flex-direction确定；

### 三、具体的设置
>### （一）、设置在flex container上的属性

>* flex-direction
>* flex-wrap
>* justify-content
>* align-items
>* align-content







#### **1.flex-direction 设置主轴方向**

```
.flex-container {
    flex-wrap:nowrap|wrap|wrap-reverse;
          }
```

 >row:将主轴设置为水平方向，如果diretion属性为ltr，则为从左到右排列；row-reverse 与之相反；

 ![png](https://raw.githubusercontent.com/Wei1191229361/wei1191229361.github.io/master/details/html%26css/.01_flex%E5%B8%83%E5%B1%80_images/baseline-1.png)
 ![](01_flex布局_images\\row-reverse.png)

>column:将主轴设置垂直方向，起点终点受书写模式(writing-model)影响;column与之相反;

![](01_flex布局_images\\column.png)
![](01_flex布局_images\\column-reverse.png)

#### **2.flex-wrap 指定 flex元素单行显示还是多行显示**

        .flex-container {
            flex-wrap:nowrap|wrap|wrap-reverse;
        }

>nowrap:flex-items被摆放到到一行,不会换行，即使元素溢出 flex 容器；

![](01_flex布局_images\\no-wrap.png)

>wrap:flex-items会自动换行，换行后在侧轴的排列依据flex-direction；

![](01_flex布局_images\\wrap.png)

>wrap-reverse:和 wrap 的行为一样,会换行，但侧轴排序相反；

![](01_flex布局_images\\wrap-reverse.png)

#### **3.justify-content  定义了浏览器如何分配顺着父容器主轴的弹性元素之间及其周围的空间。**
        .flex-container {
            justify-content: flex-start|flex-end|center|space-between|space-around;
        }
具体对齐方式与轴的方向有关。下面假设主轴为从左到右。
>flex-start（默认值）:左对齐

![](01_flex布局_images\\flex-start.png)

>flex-end:右对齐

![](01_flex布局_images\\flex-end.png)

>center:居中对齐

![](01_flex布局_images\\center.png)

>space-around:在每行上均匀分配弹性元素。相邻元素间距离相同。每行第一个元素到行首的距离和每行最后一个元素到行尾的距离将会是相邻元素之间距离的一半。

![](01_flex布局_images\\space-around.png)

>space-between:相邻元素间距离相同。每行第一个元素与行首对齐，每行最后一个元素与行尾对齐。

![](01_flex布局_images\\space-between.png)
>space-evenly:相邻元素之间的间距，主轴起始位置到第一个元素的间距,主轴结束位置到最后一个元素的间距，都完全一样。

![](01_flex布局_images\\space-evenly.png)

#### **4.align-items 侧轴方向上当前行上的弹性元素对齐方式。这个属性设置的是每一行内部的对齐方式。与align-content属性的区别在于它指定了当前Flex容器的行中的项目的对齐方式，而align-content则指定了行自身的对齐方式。**
        .flex-container {
            align-items: flex-start | flex-end | center | baseline | stretch;
        }

 >flex-start:侧轴的起点对齐。

![](01_flex布局_images\\flex-start-1.png)

 >flex-end:侧轴的终点对齐。

![](01_flex布局_images\\flex-end-1.png)

 >center:侧轴的中点对齐。

![](01_flex布局_images\\center-1.png)

 >baseline:元素的第一行文字的基线对齐。

 ![](01_flex布局_images\\baseline-1.png)

 >stretch（默认值）：如果项目未设置高度或设为auto，将占满整个容器的高度。

  ![](01_flex布局_images\\stretch-1.png)

#### **5.align-content 侧轴行的对齐方式。该属性对单行弹性盒子模型无效。**

        .flex-container {
            align-content: flex-start|flex-end|center|space-between|space-around|stretch;
        }

>flex-start:侧轴的起点对齐

![](01_flex布局_images\\flex-start-2.png)

>flex-end:侧轴的终点对齐

![](01_flex布局_images\\flex-end-2.png)

>center:侧轴居中对齐

![](01_flex布局_images\\center-2.png)


>space-around:相邻行间距离相同。在侧轴上第一行到侧轴起点的距离和最后一行到侧轴终点的距离将会是相邻行之间距离的一半。

!![](01_flex布局_images\\space-around-2.png)

>space-between:相邻行间距离相同。第一行与侧轴起点对齐，最后一行与侧轴终点对齐。

![](01_flex布局_images\\space-between-2.png)

>stretch:拉伸所有行来填满剩余空间。剩余空间平均的分配给每一行。

![](01_flex布局_images\\stretch-2.png)

>### （二）、设置在flex items上的属性

>* flex-grow
>* flex-shrink
>* flex-basis
>* flex

#### **1.flex-grow 定义当容器有剩余空间时项目的放大比例，默认为0，即如果存在剩余空间，也不放大。**
>&emsp;&emsp;假定剩余空间为x，有三个盒子flex-grow分别为1,2,3,(和大于1)。<br/>那么它们分配到的剩余空间分别是x\*1/(1+2+3)、x\*2/(1+2+3)、x\*3/(1+2+3)；<br/>
  例：<br/>
  有A、B、C三个盒子，宽都为100px，父盒子宽600px，flex-grow分别为1,2,3,那么
  * A: 100+(1/(1+2+3))*(600-300)=150;
  * B: 100+(2/(1+2+3))*(600-300)=200;
  * C: 100+(3/(1+2+3))*(600-300)=250;

![](01_flex布局_images\\flex-grow.png)

>&emsp;&emsp;如果flex-grow之和小于1,那么就会将它们的和当做1,会有剩余空间不会被分配。<br/>
例：<br/>
  有A、B、C三个盒子，宽都为100px，父盒子宽600px，flex-grow分别为0.1,0.2,0.3,那么
  * A: 100+(0.1/1)*(600-300)=130;
  * B: 100+(0.2/1)*(600-300)=160;
  * C: 100+(0.3/1)*(600-300)=190;

  ![](01_flex布局_images\\flex-grow-1.png)

>&emsp;&emsp;flex-grow 还会受到 max-width 的影响。如果最终计算完分配空间后的结果大于 max-width 指定的值，max-width 的值将会优先使用,剩余的空间会再分配。

![](01_flex布局_images\\flex-grow-3.png)



#### **2.flex-shrink 定义空间不够时各个元素如何收缩。其值默认为 1。**
>&emsp;&emsp;假定三个盒子各自宽度为a,b,c,flex-shrink为1,2,3,(和大于1),<br/>容器宽度为x,则盒子各自缩小<br/>
(a+b+c-x)\*(1\*a)/(1\*a+2\*b+3\*c),<br/>(a+b+c-x)\*(2\*b)/(1\*a+2\*b+3\*c),<br/>(a+b+c-x)\*(3\*c)/(1\*a+2\*b+3\*c),<br/>
  例：<br/>
  有A、B、C三个盒子，宽为100px，200px，300px，父盒子宽400px，flex-shrink分别为1,2,3,那么
  * A: 100-(1\*100/(1\*100+2\*200+3\*300))*(600-400)=85.71;
  * B: 200-(2\*200/(1\*100+2\*200+3\*300))*(600-400)=142.86;
  * C: 300-(3\*300/(1\*100+2\*200+3\*300))*(600-400)=171.43;

![](01_flex布局_images\\flex-shrink.png)

>&emsp;&emsp;如果和小于1,并不会收缩所有的空间，而只会收缩 flex-shrink 之和相对于 1 的比例的溢出空间。<br/>
  例：<br/>
  有A、B、C三个盒子，宽为100px，200px，300px，父盒子宽400px，flex-shrink分别为0.1,0.2,0.3,那么此时不会将超出的空间全部收缩，而是收缩200\*(0.1+0.2+0.3)/1=120
  * A: 100-(0.1\*100/(0.1\*100+0.2\*200+0.3\*300))*120;
  * B: 200-(0.2\*200/(0.1\*100+0.2\*200+0.3\*300))*120;
  * C: 300-(0.3\*300/(0.1\*100+0.2\*200+0.3\*300))*120;

![](01_flex布局_images\\flex-shrink-1.png)

>&emsp;&emsp;类似的，flex-shrink 也会受到min-width的影响；

#### **3.flex-basis 指定了 flex-items元素在主轴方向上的初始大小。**
>* 如果没有设置flex-basis属性，那么flex-basis的大小就是项目的width属性的大小
>* 如果没有设置width属性，那么flex-basis的大小就是项目内容(content)的大小

**在上面介绍flex-grow与flex-shrink时，计算每个盒子权重时使用的是width，因为没有设置flex-basis，如何设置了那么就要按flex-basis计算权重**<br/>
     例：<br/>
      有A、B、C三个盒子，宽都为100px，父盒子宽600px，flex-grow分别为1,2,3,flex-basis分别为50px,200px,100px,那么

* A: 50+(1/(1+2+3))\*(600-350)=91.7;
* B: 200+(2/(1+2+3))\*(600-350)=283.3;
* C: 100+(3/(1+2+3))\*(600-350)=225;

![](01_flex布局_images\\flex-basis.png)

#### **4.flex 是简写 flex-grow, flex-shrink与flex-basis属性 默认值是0 1 auto**
>flex 属性可以指定1个，2个或3个值。

**单值语法: 值必须为以下其中之一:**
* 一个无单位数(<number\>): 它会被当作<flex-grow\>的值。
* 一个有效的宽度(width)值: 它会被当作 <flex-basis\>的值。
* 关键字none, auto,或initial.

**双值语法:**
 * 第一个值必须为一个无单位数，并且它会被当作<flex-grow\>的值。
 * 第二个值必须为以下之一：<br/>
一个无单位数：它会被当作<flex-shrink\>的值。<br/>
一个有效的宽度值: 它会被当作<flex-basis\>的值。


**三值语法:**
* 第一个值必须为一个无单位数，并且它会被当作<flex-grow\>的值。
* 第二个值必须为一个无单位数，并且它会被当作 <flex-shrink\>的值。
* 第三个值必须为一个有效的宽度值， 并且它会被当作<flex-basis\>的值。

### 四、总结
>&emsp;&emsp;暂时就整理这么多以后有空再继续深入研究,<br/>主要分清主轴侧轴、align-content与align-items;flex-grow与flex-shrink、flex-basis的计算关系
