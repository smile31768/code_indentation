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
  可能大家在编写简单程序的时候不太能理解缩进的意义。但是当代码繁杂起来的时候一个正确的缩进就显得尤为重要了。一个正确规范的缩进不仅能使别人更容易读懂你的代码，更重要的是能使你少写很多bug！事实上，绝大多数的IDE在你编写代码的时候都会进行自动缩进。但即使有自动缩进的功能存在，我们也依旧需要了解正确规范的缩进格式，因为自动缩进仅在编写新代码时生效，在debug的过程中很多时候是不会再次帮你缩进的。废话不多说，上对比
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
```C++
#include <stdio.h>/*无换行*/int main(){/* 局部变量定义 */int i, j;for (i = 2; i < 100; i++) {for (j = 2; j <= (i / j); j++){if (!(i % j)) break; /* 如果找到，则不是质数*/}if (j > (i / j)){printf("%d 是质数\n", i);}}return 0;}
```
看看上面几个案例，如果使用了多重嵌套的语句，不缩进或者未按照规范缩进你能快速辨认哪个语句在哪一个花括号内吗？至于没换行的那个……两分钟内能看得懂的建议直接入职华为。觉得都没区别的出门左转。觉得区别大了去了那么你可以继续往下学习缩进了！
## 如何正确按照规范缩进你的代码？
### (一)Tab键是缩进代码的工具
  很多比较细心的编程初学者在学习编程的时候可能会注意到代码缩进的问题，在一些没有自动缩进的地方会邯郸学步一般使用空格进行缩进。但是由于不知道缩进的具体格式方法，导致写出来的代码参差不齐
```C++
#include <stdio.h>
int main()
{
    int a;
   float b;
    printf("Hello World!");
   return 0;
}
```
  这样的代码也能运行，但是代码量一多其实并不美观。事实上，目前我见过一般缩进的单元字符数为4个字符，其中也有8个或者2个甚至3个字符缩进的存在（但是我并不喜欢）。
用空格固然可以对代码进行缩进，但是使用Tab键缩进更为高效。

**优点如下**</br>
1. 首先，Tab键按一下当你空格按四下</br>
2. Tab可以对多行进行操作。举个例子，当你想要缩进一整个代码块时，你可以全选整个代码块，按下Tab即可对整块进行缩进，而不用一行一行地敲打空格</br>
3. 以上两点还不够你使用Tab？</br>
  综上，我建议大家使用Tab进行代码缩进。

`附1：使用Shift+Tab可以撤销缩进，同样可以同时多行操作`</br>
`附2：使用Tab键虽然方便，但也会导致一些不可预料的问题（在Python中，此问题尤为严重），因此建议将Tab设置为“使用Tab替代四个空格”，具体设置方法不在此展开讲，详细方法自己百度`
### (二)在何时需要缩进？
**(1) 新建函数时，函数对应花括号中间所有代码往前缩进四个字符**
我们用一个最简单的程序进行演示：
```C++
int main()
{
    int a;                      //花括号中间的所有代码往前
    int b;                      //缩进一个Tab（四个字符），
    printf("Helloworld!");      //上下花括号对齐前方int。
}
```
同理，当一个程序有多个函数，每个函数也应该如上处理：
```C++
#include <stdio.h>
int main()
{
    void print();
    int a;
    int b;
    print();
}

void print()
{
    printf("Helloworld!");
}
```
**(2) 在遇到if，else，for，do，while等语句时，花括号中间所有代码再往前缩进一个Tab**
```C++
//简单while语句
#include <stdio.h>
int main()
{
    int i = 1;
    int sum = 0;
    while (i <= 100)
    {
        sum = sum + i;      //此处相对其他语句往前再缩进一个
        i++;                //Tab的距离，花括号对准while
    }
}
```
当多种语句嵌套时，处理方法同上：
```C++
#include <stdio.h>
int main()
{
    int n;
    for (n = 100; n <= 200; n++)
    {
        if (n % 3 == 0)
        {
            continue;       //再相对if往前缩进一个Tab
        }
        printf("%d",n);
    }
    printf("\n");
    return 0;
}
```
**※特殊情况：使用switch……case时，case相对switch不缩进！**
这个特殊情况可不是我说特殊他就是特殊的，这是微软老大哥告诉我的。</br>
`https://msdn.microsoft.com/zh-cn/library/k0t5wee3.aspx`
```C++
#include <stdio.h>
int main()
{
    char grade;
    scanf ("%c",&grade);
    switch (grade)
    {
    case 'A':                   //case向上对齐switch，不缩进
        printf ("85-100");
        break;
    case 'B':
        printf ("70-84");       //此处代码块如(2)，相对case
        break;                  //向右缩进一个Tab。
    case 'C':
        printf ("60-70");
        break;
    }
}
```
