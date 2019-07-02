## 03 CSS 变量

### 实现目标

使用 JS 修改 CSS 变量的值

### 功能点

1. 有三个`input`分别控制了`img`的三个属性，通过 JS 代码实现对这些属性的修改

### 实现细节

1. 已给出的 CSS 结构中，三个属性分别对应了以`--`开头的 CSS 变量，通过 JS 代码控制这些变量就行
2. HTML 结构中，两个`input`有自定义的`data-sizing`属性，代表了取值的单位
3. 通过这个属性获得属性的单位，和`input`的`value`拼在一起，使用`document.documentElement.style.setProperty`设置到标签中
4. 把更新方法注册到`change`,`mousemove`两个事件中

### 知识点

1. DOM节点的`dataset`属性包含所有`data-`作为前缀的属性，在访问时对于多个`-` 的属性，例如`date-user-id`在`dataset`中以`dataset[userId]`访问，也就是小驼峰的形式

### 参考

1. [HTMLElement.dataset属性](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dataset)