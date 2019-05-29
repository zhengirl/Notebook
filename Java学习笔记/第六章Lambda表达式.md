## Lambda表达式

>Lambda是这些年来Java语言最激动人心的一个变化。Lambda是一个可传递的代码块，可以在以后执行一次或多次。

### 一、基本概念

Lambda表达式的形式：参数，箭头(->)以及一个表达式。

```java
// 将计算方法放在{}中
(String first, String second) ->
{
  if(first.length() <second.length()) return -1;
  else if(first.length()>second.length()) return 1;
  else return 0;
}

// 无参数的表达形式,括号不能省略
() -> {for (int i = 100;i>=0;i--) System.out.println(i);}
```

无需指定Lambda表达式的返回类型，Lambda表达式的返回类型总是会由上下文推导得出。

### 二、函数式接口

对于**只有一个抽象方法**的接口，需要这种接口的对象时，就可以提供一个lambda表达式。这种接口称谓函数式接口。
lambda表达式可以转换为接口，具体的语法很简短。

```java
Timer t = new Timer(1000, event ->
   {
    System.out.println("At the tone, the time is "+ new Date());
    })
```

实际上，在Java中，对lambda表达式所能做的也只是转换为函数式接口。

### 三、方法引用

有时，可能已经有现成的方法可以完成你想要传递到其他代码的某个动作。例如，你希望只要出现一个定时器对象就打印这个事件对象。则可以调用：

```java
Timer t = new Timer(1000, event->System.out.println(event));
```

也可以吧println方法直接传递到Timer构造器：如下，

```java
Timer t=new Timer(1000, System.out.::println);
```

表达式System.out.::println是一个方法引用，等价于`x -> System.out.println(x)`.

### 四、变量作用域

通常，你可能希望能够在lambda表达式中访问外围方法或类中的变量。lambda表达式的代码可能会在repeatMessage调用返回很久以后才运行，而那时这个参数变量已经不存在了。如何保留函数只中的变量呢？

首先是lambda表达式的三个部分：

- 一个代码块
- 参数
- 自由变量的值，这是指非参数而且不在代码中定义的变量

自由变量表示lambda表达式的数据结构必须存储自由变量的值，在这里就是字符串"Hello"。称作它被lambda表达式捕获(captured)。

lambda表达式可以捕获外围作用域中变量的值，在java中，要确保所捕获的值是明确定义的，而且有一个重要的限制。在lambda表达式中，只能引用值不会改变的变量。**不能改变捕获的变量**，因为如果在lambda只中改变变量，并发执行多个动作时就会不安全。

### 五、处理lambda表达式

使用lambda表达式的重点是延迟执行(***deferred execution***),毕竟，如果想要立即执行代码，完全可以直接执行，而无需把它包装在一个lambda表达式中。之所以希望以后再执行代码，这有很多原因，如：

- 在一个单独的线程中运行代码；
- 多次运行代码；
- 在算法的适当位置运行代码(例如，排序中的比较操作)
- 发生某种情况时执行代码(如，点击了一个按钮，数据到达，等等)
- 只在必要时才运行代码。

