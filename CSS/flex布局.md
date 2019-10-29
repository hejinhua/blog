## 一、基本概念

![在这里插入图片描述](https://img-blog.csdnimg.cn/20181031181447766.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjE4NjUxMw==,size_16,color_FFFFFF,t_70)
```css
	//任何一个容器都可以指定为Flex布局。
	.box{
	  display: flex;
	}
	//行内元素也可以使用Flex布局。
	.box{
	  display: inline-flex;
	}
	//注意，设为Flex布局以后，子元素的float、clear和vertical-align属性将失效。
```
## 二、容器属性
**1. flex-direction**

flex-direction 决定项目的排列方向

```css
	.box {
	  flex-direction: row | row-reverse | column | column-reverse;
	}
```
**2. flex-wrap**

默认情况下，项目都排在一条线（又称”轴线”）上。flex-wrap 属性定义，如果一条轴线排不下，如何换行。

```css
	.box{
	  flex-wrap: nowrap | wrap | wrap-reverse;
	}
```
**3. flex-flow**

flex-flow 属性是 flex-direction 属性和 flex-wrap 属性的简写形式，默认值为 row nowrap。

```css
	.box {
	  flex-flow: <flex-direction> || <flex-wrap>;
	}
```
**4. justify-content**

justify-content 属性定义了项目在水平方向的对齐方式。

```css
	.box {
	  justify-content: flex-start | flex-end | center | space-between | space-around;
	}
```
**5. align-item**

align-item 属性定义了项目在垂直方向的对齐方式。

```css
	.box {
	  align-items: flex-start | flex-end | center | baseline | stretch;
	}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181031183633999.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjE4NjUxMw==,size_16,color_FFFFFF,t_70)

 **3.6  align-content属性**
 
align-content属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

```css
	.box {
	  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
	}
```

## 三、项目的属性
**1.  order**

order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。
```css
	.item {
	  order: <integer>;
	}
```
**2.  flex-grow**

flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。

```css
	.item {
	  flex-grow: <number>; /* default 0 */
	}
	//如果所有项目的flex-grow属性都为1，则它们将等分剩余空间（如果有的话）。如果一个项目的flex-grow属性为2，其他项目都为1，则前者占据的剩余空间将比其他项多一倍。
```
**3.  flex-shrink**

flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。

```css
	.item {
	  flex-shrink: <number>; /* default 1 */
	}
```
**4. flex-basis**

flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。

```css
	.item {
	  flex-basis: <length> | auto; /* default auto */
	}
	/*它可以设为跟width或height属性一样的值（比如350px），则项目将占据固定空间。*/
```
**4.5  flex属性**

flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto。后两个属性可选。
```css
    .item {
      flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
    }
```
该属性有两个快捷值：auto (1 1 auto) 和 none (0 0 auto)。
**4.6 align-self属性**

align-self 属性允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items 属性。默认值为 auto，表示继承父元素的 align-items 属性，如果没有父元素，则等同于 stretch。等同于 align-items

```css
	.item {
	  align-self: auto | flex-start | flex-end | center | baseline | stretch;
	}
```
