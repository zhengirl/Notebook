### 第八章 Python函数

一、序列解包

> d=1,2,3
>
> a,b,c = d

二、参数

1、必须参数 调用时会用到 

2、关键字参数，提高代码的可读性

> def add(x,y):
>
> 	result = x+y
>
> 	print(result)
>
> c = add(y=3,x=2)

3、默认参数 

> def print_student_files(name, gender='男',age=18,
>
> 					college='人民路小学'):
>
> 	pass
>
> print_student_files('鸡小萌')  #不改变默认参数
>
> print_student_files('石敢当', '女'，'16')

>

 