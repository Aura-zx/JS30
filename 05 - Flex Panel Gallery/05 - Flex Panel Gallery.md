## 05 Flex 面板美术馆

### 实现目标

使用flex布局完成一个美术馆效果

### 功能点

1. 使用flex布局
2. 中间的文字要放大
3. 占比要放大
4. 上下的文字出现

### 实现细节

1. 加上flex布局即可，很简单
2. 在`点击`的时候给`panel`添加/移除`.open`类，实现字号/宽度的放大和恢复
3. 上下的文字是使用`transform:translateY(-100%)`的形式隐藏的，在`动画结束后`，给`panel`里的上下两个`p`标签添加`.open-active`类添加`transform:translateY(0)`的方式让他们重新出现
4. 添加/移除类使用`element.classList.toggle`方法

### 知识点

1. DOM节点的`toggle`方法有两个参数，在只有一个参数时是切换效果；如果类存在则删除并返回`false`，如果不存在则添加并返回`true`；两个参数：如果第二个参数的计算结果为`ture`，则添加指定的类，如果计算结果为`false`，则删除它。

### 参考

1. [HTMLElement.classList](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/classList)