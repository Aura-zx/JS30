## 02 JS和CSS实现钟表效果

### 实现目标

用JS和CSS实现时钟的时分秒的指针动画效果

### 功能点

1. CSS样式
2. 根据当前时间计算时针的角度
3. 设置旋转动画

### 实现细节

1. 思路是通过每一秒设置三个指针的`transform`属性为rotate，实现指针的旋转。
2. 初始时指针的位置为-90度，在计算需要旋转的角度时需要加上这个角度。
3. `board-radius`可以将区域设置为圆形。
4. `transform-origin`可以改变变换的中心，需要将它设置为100%，默认为50%，此时旋转就是围绕着指针中心进行。
5. 使用`setInterval`函数实现每1s计算并设置一次三个指针的属性。


### 知识点

1. `transform-origin`属性可以由1、2或者3个值，值有两种类型，一种是数值，长度或者百分比，另一种是字符串，关键词，表方位的单词(top/bottom/left/right/center)等，取值则是他们的组合。

### 参考

1. [transform-origin](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)