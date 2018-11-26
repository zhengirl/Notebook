 ### python网络课第三课：数据类型

一、运算符号 

> // 整除 2//2=1 1//2=0  (只保留整数部分)
>
> / 除法 2/2=1.0 1/2=0.5

二、不同进制的数相互转换

| 二进制 | 八进制 | 十进制 | 十六进制 |
| :----: | :----: | :----: | :------: |
|  0bXX  |  0oXX  |   XX   |   0xXX   |
| bin()  | oct()  | int()  |  hex()   |

三、布尔值

>int(False)=0
>
>int(True)=1
>
>bool(1)=True
>
>bool(-1)=True #凡是非零数布尔值均为真
>
>bool(0)=False
>
>bool('')=False
>
>bool([])=False
>
>bool({})=False
>
>bool(None)=False  # (一系列空值都是False)

四、Python的字符数据类型：单引号、双引号、三引号

单引号与双引号：单双引号必须成对出现

在字符串本身内容中含有引号时，用另一种引号来结尾,内容就可正常显示

>"Let's go."
>
>'Let"s go.'

三引号：可换行的字符串

> """  """
>
> ''' '''

四、转义字符

| \n   | \r   |
| ---- | ---- |
| 换行 | 回车 |

> **print(r'c:\north:\north')**   //当字符串前面加一个r后，这个普通字符串变成原始字符串
> c:\north:\north

字符串的定位

> "hello world"[0]
>
> h
>
> "hello world"[-1]
>
> d
>
> "hello world"[-5]
>
> w