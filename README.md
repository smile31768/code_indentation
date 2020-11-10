# 代码缩进
## 什么是代码缩进？
代码缩进指的是我们在编写编程语言的过程中，在一些特定行的代码左端空出一部分长度，使得更加清晰地从外观上看出程序的逻辑结构，使得代码更加易于阅读。
```C++
#include <stdio.h>
int main()
{
    printf("Hello World!");
}
```
如上代码，在printf前面四个空格便是代码缩进
## 为什么要代码缩进？
可能大家在编写简单程序的时候不太能理解缩进的意义。但是当代码繁杂起来的时候一个正确的缩进就显得尤为重要了。废话不多说，上对比
```C++
#include <stdio.h>
//缩进示例
int main()
{
	/* 局部变量定义 */
	int i, j;
	for (i = 2; i < 100; i++) 
	{
		for (j = 2; j <= (i / j); j++)
		{
			if (!(i % j)) break; // 如果找到，则不是质数
		}
		if (j > (i / j))
		{
			printf("%d 是质数\n", i);
		}
	}
	return 0;
}
```
```C++
#include <stdio.h>
//不缩进示例
int main()
{
/* 局部变量定义 */
int i, j;
for (i = 2; i < 100; i++) 
{
for (j = 2; j <= (i / j); j++)
{
if (!(i % j)) break; // 如果找到，则不是质数
}
if (j > (i / j))
{
printf("%d 是质数\n", i);
}
}
return 0;
}
```
```C++
#include <stdio.h>
//未按规范缩进
int main()
{
	/* 局部变量定义 */
	int i, j;
	for (i = 2; i < 100; i++) 
	{
	    for (j = 2; j <= (i / j); j++)
		{
		if (!(i % j)) break; // 如果找到，则不是质数
		}
		if (j > (i / j))
		{
		printf("%d 是质数\n", i);
		}
	}
	return 0;
}
```
看看上面两个案例，如果使用了多重嵌套的语句，不缩进或者未按照规范缩进你能快速辨认哪个语句在哪一个花括号内吗？觉得没区别的出门左转。觉得区别大了去了那么你可以继续往下学习缩进了！
## 如何正确按照规范缩进你的代码？
### Tab键是缩进代码的工具
很多比较细心的编程初学者在学习编程的时候可能会注意到代码缩进的问题，在一些没有自动缩进的地方会为了美观使用空格进行缩进。但是由于不知道缩进的具体标准，导致写出来的代码参差不齐
```C++
#include <stdio.h>
int main()
{
   int a;
    printf("Hello World!");
     return 0;
}
```
这样的代码也能运行，但是代码量一多其实并不美观。事实上，目前大多数缩进的单元字符数为4个字符，其中也有8个或者2个甚至3个字符（即俗称空格）缩进的存在（但是我并不喜欢）。
用空格固然可以对代码进行缩进，但是使用Tab制表符更为高效
>	优点如下</br>
	1.首先，Tab制表符按一下当你空格按四下</br>
	2.Tab可以对多行进行操作。举个例子，当你想要缩进一整个代码块时，你可以全选整个代码块，按下Tab即可对整块进行缩进，而不用一行一行地敲打空格</br>
	3.以上两点还不够你使用Tab？
综上，我建议大家使用Tab进行代码缩进。
<
>附
