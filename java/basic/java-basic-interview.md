### 如何理解面向对象？
要学好程序设计，我们首要的必修课就是程序设计中的面向对象相关的原理和基本概念。


何为面向对象？

要理解面向对象，我们先来看看与面向对象相对应的另外一种程序设计方法：面向过程。

面向过程的编程的基本构成便是“过程”，过程实现的方式就是“函数”，我们通过不同函数来实现不同的功能，并按照程序的执行顺序调用相应的函数，组成一个完整的可以运行的应用程序。我们可以通过把不同的功能在不同的函数中实现或者给函数传递不同的参数来实现不同的功能，这是面向过程中模块化设计的原理。

但是面向过程有很多问题，当我们总是按照教科书上的小例子来学习程序设计时是永远也体会不到面向过程中存在的这些问题的，反而会觉得面向过程更简单，更容易理解。而事实是当我们设计一些大型的应用的时候你将会发现使用面向过程编程是多么的痛苦和无奈，代码极难维护，我们不得不为相似功能设计不同的函数，天长日久，代码量越来越大，函数越来越多，而重复的代码越来越多，噩梦就此产生。

于是乎产生了另外一种设计思想：面向对象，从此程序员发现编程是多么快乐的一件事情。我们可以把现实世界的很多哲学思想或者模型应用于编程，这是计算机的一次伟大的革命。那么究竟何为面向对象？要理解这两个重要的字“对象“，我们首先需要理解一下类和实例：

举一个简单的例子，大家都会下五子棋，我们就以开发一个五子棋的游戏来讲解面向过程和面向对象最本质的区别，在早期以面向过程为主要开发方法时，我们是这样来设计这个游戏的：

1) 开始游戏

2) 黑方出子

3) 绘制画面

4) 判断胜负

5) 白方出子

6) 绘制画面

7) 判断胜负

8) 循环2、3、4、5、6、7步

9) 输出结果

最后将每一个步骤作为一个处理函数开发出来，每次运行都调用一遍函数(或者过程)。面向过程最关键的概念就是“过程”，所以程序运行都是一步接一步，从上往下。

而面向对象的设计则是从另外的思路来解决问题。整个五子棋可以分为：
1) 黑白双方：负责出子和悔棋

2) 棋盘系统：负责绘制画面

3) 规则系统：负责判定诸如犯规、输赢等

4) 输入输出系统：负责接收黑白子放的位置信息和输出游戏过程中的相关信息

这就是面向对象，更强调将程序模块化，我们甚至可以将该程序抽象出来使其适用于五子棋和围棋(它们除了规则不一样以外没有其它区别，那么我们只需要修改规则系统便可轻易支持围棋)。

何为类？

类就是“一类东西”，比如“车”是一类东西，“汽车”，“自行车”也是一类东西，“大众汽车”，“永久自行车”也是一类东西。

何为实例？

实例就是明确告知哪一类东西的哪一个，比如“小明家的桑塔纳Vista”，或者“编号为1389756的永久牌自行车”就属于一个实例。

何为对象？

在面向对象的程序设计中，“一切皆是对象”(记住这句话，对面向对象理解得有多深取决于对这句话的理解有多深)。一个类是一个对象，一个实例是一个对象，一个变量也是一个对象，甚至一个数据类型，也都可以视为一个对象。

对象有什么特性？

对象不同于过程的最基本的特质有两点：

1) 对象有方法，比如车可以“开”，可以“停”，可以“刹车”，这些属于方法。

2) 对象有属性，比如车有“重量”，“排量”，“轴距”，“油耗”等，这些属于属性。

对于属性，这在面向过程中是没有相关概念与之对应的，而对于方法，方法本身来说就是一段处理程序，方法与面向过程的函数其实是类似的(方法和函数都由一段代码组成，可以包括参数，可以有返回值或没有返回值)，它们之间唯一的区别在于函数是不存在公有私有一说的，而方法却有类型修饰符(public, private, protected等)，这种类型修饰符直接决定了该方法能不能被别的子对象使用。

何为子对象呢？

这里牵涉着面向对象另一个非常重要的特性：继承。简单理解继承就是“子承父业”，与生物学上的继承，遗传的概念没有区别。就拿人类来说，父亲有的方法(如走，跑，跳，吃，睡等)同样儿子也可以有，儿子还可以自创一个自己的方法(如射击，冲浪)，同样，儿子也有可能某些方法不能用(比如残废，不能走，跑，跳，但可以吃，睡)，这是继承。

关于继承，有两个重要的概念大家容易混淆：重写和重载，二者区别在于：
重写：父亲走路是向前走的，儿子重写父亲走路的动作，横着走。(虽然都是走，结果完全不同)，这属于继承的范畴。
重载：对同一个类，比如父亲，同一个方法可以有多种实现手段，比如跑，可以快跑，可以慢跑，可以短跑，可以长跑，那么一个跑“Run”就可以对应4个实现手段。这是重载，特别注意的是重载只针对一个对象而言，与继承没有任何关系。

现实生活中还有一个很有趣的现象是：父亲是儿子的父亲，同样父亲也是爷爷的儿子，所以父亲这个对象它有时候也是儿子，那么还有可能是丈夫 。这表示一个对象可以有多种形态，这就是“多态”。

关于面向对象的基本概念再次总结如下：

1) 一切皆是对象

2) 类表示一类事物

3) 实例表示一类事物中明确指定的那个

4) 对象有方法和属性

5) 对象可以被继承

6) 一个对象可以有多种形态
