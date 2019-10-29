### 原理
```
.yl {
    width: 0;
    height: 0;
    border-color:red blue green yellow;
    border-style: solid;
    border-width: 40px;
}
```
![](https://img-blog.csdnimg.cn/20181129150937765.png)

我们看到有上下左右四个三角形了。
如果, 我们把4种颜色, 只保留一种颜色, 余下3种颜色设置为透明,那么就是一个三角形了。


### 直角三角形
1. 
```
.left-bottom {
   width: 0;
   height: 0;
   border-bottom: 50px solid red;
   border-right: 100px solid transparent;
}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181129145425949.png)

2. 

```
.right-bottom {
    width: 0;
    height: 0;
    border-bottom: 50px solid red;
    border-left: 100px solid transparent;
}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181129145936509.png)

3. 
```
.top-right {
    width: 0;
    height: 0;
    border-top: 50px solid red;
    border-left: 100px solid transparent;
}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181129150014788.png)

4. 
```
.top-left {
    width: 0;
    height: 0;
    border-top: 50px solid red;
    border-right: 100px solid transparent;
}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181129150139281.png)

### 等腰三角形
```
 .up {
    width: 0;
    height: 0;
    border-left: 50px solid transparent;
    border-right: 50px solid transparent;
    border-bottom: 100px solid red;
}
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181129150610668.png)
