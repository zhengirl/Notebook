### java的类

### 一 、类

​	Java中**所有函数**都属于某个类的方法。（故Java中的main方法必须有一个外壳类，Java中`main`函数必须是静态的）

### Java中的注释

三种注释方法：

- 最常用的的是`//`,其注释内容从`//`开始到本行结尾。
- 长篇注释：每行的注释前面标记`//`，或者使用`/*`和`*/`将较长的注释括起来，这种方式可以自动生成文档。

### Java中的变量

Java中每一个变量都有一个类型。Java中变量声明时需要初始化，以免出现不必要的麻烦。

```java
int i，j；//不提倡使用，逐一声明每一个变量可以提高程序的可读性
```

**常量**

```java
final double CM_PER_INCH = 2.54
```

关键字final表示这个变量只能被赋值一次，一旦被赋值以后，就不能再更改了。

**类常量**

类常量可以在一个类的多个方法中使用。

```Java
public class Constants2
{
    public static final double CM_PER_INCH = 2.54;
    
    public static void main(String[] args)
    {
        xxx;
    }
        
}
```

**Java的操作符**

++，--这类自增自减运算符不要在表达式中使用，这样的代码让人困惑，也会带来烦人的bug。