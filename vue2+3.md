## vue2+3

### day2

案件修饰符 

@keyup.enter 使用键盘回车时候会添加

v-model

.trim去空格 .number收集数字

@事件.stop 阻止冒泡，避免在父组件中会冒泡

@事件.prevent 主旨默认行为



v-bind对样式的控制



![image-20230903011111853](/Users/kad/Library/Application Support/typora-user-images/image-20230903011111853.png)

可以实现鼠标放上去可以显示一些行内样式

![image-20230903011256247](/Users/kad/Library/Application Support/typora-user-images/image-20230903011256247.png)



v-model运用与其他表单元素

![image-20230903011453186](/Users/kad/Library/Application Support/typora-user-images/image-20230903011453186.png)



计算属性

![image-20230903011731818](/Users/kad/Library/Application Support/typora-user-images/image-20230903011731818.png)



computed vs methods

计算属性一般对数据处理，方法一般是业务处理

对于性能来说，计算属性具有缓存特性

![image-20230903012312507](/Users/kad/Library/Application Support/typora-user-images/image-20230903012312507.png)

![image-20230903012456903](/Users/kad/Library/Application Support/typora-user-images/image-20230903012456903.png)

![image-20230903012620368](/Users/kad/Library/Application Support/typora-user-images/image-20230903012620368.png)

filter过滤函数

![image-20230903012738473](/Users/kad/Library/Application Support/typora-user-images/image-20230903012738473.png)

watch 监视器

![image-20230903013126503](/Users/kad/Library/Application Support/typora-user-images/image-20230903013126503.png)

![image-20230903013204652](/Users/kad/Library/Application Support/typora-user-images/image-20230903013204652.png)

day3

vue的生命周期

![image-20230903013341043](/Users/kad/Library/Application Support/typora-user-images/image-20230903013341043.png)





day4

style只作用与当前页面

style加上scoped

data是一个函数

组件中的通信

![image-20230903014340764](/Users/kad/Library/Application Support/typora-user-images/image-20230903014340764.png)

![image-20230903014400993](/Users/kad/Library/Application Support/typora-user-images/image-20230903014400993.png)

![image-20230903014448264](/Users/kad/Library/Application Support/typora-user-images/image-20230903014448264.png)

![image-20230903014549118](/Users/kad/Library/Application Support/typora-user-images/image-20230903014549118.png)

![image-20230903014624476](/Users/kad/Library/Application Support/typora-user-images/image-20230903014624476.png)

.sync修饰符

![image-20230903015120203](/Users/kad/Library/Application Support/typora-user-images/image-20230903015120203.png)

![image-20230903015850184](/Users/kad/Library/Application Support/typora-user-images/image-20230903015850184.png)

![image-20230903020216018](/Users/kad/Library/Application Support/typora-user-images/image-20230903020216018.png)

![image-20230903020406881](/Users/kad/Library/Application Support/typora-user-images/image-20230903020406881.png)



day5

自定义指令

![image-20230903020734968](/Users/kad/Library/Application Support/typora-user-images/image-20230903020734968.png)

插槽

作用可以让组件内部的一些结构支持自定义

![image-20230903020913937](/Users/kad/Library/Application Support/typora-user-images/image-20230903020913937.png)

![image-20230903021350003](/Users/kad/Library/Application Support/typora-user-images/image-20230903021350003.png)

![image-20230903022708742](/Users/kad/Library/Application Support/typora-user-images/image-20230903022708742.png)

![image-20230903023054122](/Users/kad/Library/Application Support/typora-user-images/image-20230903023054122.png)

![image-20230903025438868](/Users/kad/Library/Application Support/typora-user-images/image-20230903025438868.png)