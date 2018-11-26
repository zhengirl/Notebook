### oop 面向对象

#### 单词解释：

class（类）：告诉python去创建一个新类型

object（对象）：事物的基本类型或者事物的实例化

instance（实例）：通过python创建一个类所获得的

def：用来在类中定义一个函数

self：在一个类包含的函数中，self是一个用来访问实例或对象的变量

inheritance：表示一个类可以继承另一个类的特征，就像父母和孩子的关系

composition：表示一个类可以包含其他类，就像汽车和轮子的关系

attribute：类所拥有的特性

is-a：表示一个东西继承自另一个东西，如鲑鱼和鱼

has-a：表示由其他事情或有一个特征，如“鲑鱼有嘴”

#### 短语解释

`class X（Y）`：创建一个 叫X的类，并继承Y

` class X（object):def __init__(self,J):`:类X有一个`__init__`方法，该方法有self和J两个参数；

`class X（object）：def M（self，J）`：类X有一个叫M的函数。该函数有self和j两个参数

`foo=X()`:给foo赋值为类X的一个实例

`foo.M(J)`:从foo里调用M函数，传递的参数为self和J；

`foo.K=Q`:从foo里调用K属性，并将其设置为Q