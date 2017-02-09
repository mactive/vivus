## 文件说明

* lines.svg sketch.app 制作出来的
* lines_animated.svg 是 经过 https://maxwellito.github.io/vivus-instant/ 转换的svg-animate文件

## 原理

然后将 `svg` 标签中的 <cricle> <rectangle> 都换成 <path>, 然后配合一些`svg`的内置style,

然后用vivus的js解释一遍就绘制出来了.

最好玩的是 lines_animated.`svg` 在mac里是可以直接预览的  ~~而且有动画效果?~~ 额,难道是错觉



## 绘制顺序
vivus 绘制顺序就是按照图层顺序从back的图层front的到依次绘制, 如果你选择了{types:"oneByOne"}的话


## 如何让填充颜色最后出现 
[参考这里](https://github.com/maxwellito/vivus/blob/master/hacks.md)
简单讲原理就是先给整个`svg`的opacity设为0, 并设置好transition时间, 然后在vivus结束之后的回调里将获取`svg`对象的classlist,
把opacity变成1,填充颜色就出现了. 因为对于 `svg` opacity不影响 path的绘制