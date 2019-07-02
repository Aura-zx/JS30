## 01 模拟爵士鼓的敲鼓

### 实现目标

模拟一个打鼓的页面，按下键盘上的ASDFGHJKL这几个键时，发出声音，页面上对应按钮的按钮触发动画效果，并发出提前绑定的声音。

### 功能点

1. 绑定键盘`keydown`事件
2. 播放声音
3. 改变样式触发动画


### 实现细节

1. HTML结构：有一个div区域负责页面视觉的展现，其中包括每个按键的div区域，还有每个按键对应的audio元素，负责声音的播放，它们有对应按键的ASCII码值作为元素的`data-key`属性的值。
2. 当按键按下时需要分别获取div和audio元素，然后进行动画效果的展示和声音的播放。
3. 播放时遇到的问题是，连续两次按下同一个按钮时，第二次会等待第一次播放完毕后才会播放，所以在每一次调用play方法后，要将audio元素的currenTime设置为0，下一次按下时就会从头播放声音。
4. 动画效果遇到的问题是，在`动画效果完成之后`需要删除之前添加的类，按下后的效果一直存在在页面上，那么它需要绑定的事件是`transitionend`。

### 知识点

1. `kbd`(HTML Keyboard Input element)，会生成一个inline的元素，通常表示来自键盘、语言或者其它文本输入设备的输入，已不推荐使用。
2. `transition`属性中集合了`transition-property`,`transition-duration`,`transition-timing-function`,`transition-delay`这4个属性。`transition-timing-function`定义了参与transform的CSS属性中间值是如何计算的，有几个默认的方法定义了匀速变化(linear)，先快后慢(ease-out)，先慢后快(ease-in)，前后快中间慢(ease-in-out)，这些预置的方法都是由`cubic-bezier`函数实现的，这个函数是`贝塞尔曲线`的生成函数，共有四个参数，分别代表了坐标轴中两个点的x,y值。
3. `data-*`属性，用户自定义属性，可以加在HTML标签中，放置一些开发者自定义的数据。

### 参考

1. [kbd标签](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/kbd)
2. [transition属性](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
3. [可视化的cubic-bezier函数](http://cubic-bezier.com/)
4. [data-*属性](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*)
5. [audio标签](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
6. [transitionend事件](https://developer.mozilla.org/en-US/docs/Web/Events/transitionend)