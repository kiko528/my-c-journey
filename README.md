# my-c-journey
我的C语言学习成长记录
2026/9/22
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main()
{
	int a = 0;
	float b = 0;
	scanf("%d""%f", &a, &b);//有几个占位符就对应几个变量
	float c = a + b;//计算应写在输入之后
	printf("%f\n", c);


	return 0;
}

int main()
{
	int a = 0;
	int b = 0;
	while (scanf("%d""%d", &a, &b) == 2)//while后面不能跟分号，分号表示循环结束，双等号表示判断，一个为赋值
	{
		int c = a + b;
		printf("c = %d\n", c);
	}//while为函数语句，大括号里面的变量属于这个代码块局部变量


	return 0;
}
日期：2026年9月22日
今日学习内容
基础输入输出：学习了 scanf 和 printf 的基本用法。
变量类型：练习了 int（整型）和 float（浮点型）的定义与使用。
循环结构：初步接触了 while 循环，实现了多次输入求和的功能。
作用域：理解了局部变量的概念（大括号 {} 里面的变量只在该代码块内有效）。
️ 踩坑记录与注意事项
scanf 的占位符：scanf 里有几个占位符（如 %d、%f），后面就要对应几个变量的地址（&a, &b）。
计算顺序：计算逻辑（如 c = a + b）必须写在输入（scanf）之后，否则计算的是初始值 0。
while 循环语法：
while 后面不能直接加分号 ;，否则循环体为空，程序会死循环或无反应。
判断相等要用双等号 ==，单等号 = 是赋值。
VS 编译问题：在 Visual Studio 中使用 scanf 需要在第一行加上 #define _CRT_SECURE_NO_WARNINGS，否则会报错。


#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
int main()
{
	//int a = 0;
	//scanf("%d", &a);//scanf一定要记得取地址操作符，除了数组
	//if (a % 2 == 1)
	//	printf("奇数\n");
	//else
	//	printf("偶数\n");

	/*int age = 0;
	scanf("%d", &age);
	if (age >= 18)
	{
		printf("已成年\n");
		printf("可以谈恋爱了\n");
	}
	else
	{
		printf("未成年\n");
		printf("好好学习，天天向上\n");

	}*/
	/*int a = 0;
	scanf("%d", &a);
	if (a == 0)
		printf("输入的数字是0\n");
	else if (a > 0)
		printf("正数\n");
	else
		printf("负数\n");*/

	/*int a = 0;
	scanf("%d", &a);
	if (a > 0)
	{
		if (a % 2 == 1)
			printf("奇数\n");
		else
			printf("偶数\n");
	}
	else
		printf("非正数\n");*/
日期：2026年9月23日
今日学习内容
if-else 基本结构：学习了如何使用 if 和 else 进行二选一的判断（如判断奇偶、是否成年）。
多分支判断：掌握了 if - else if - else 结构，用于处理多种情况（如判断正数、负数、零）。
嵌套 if 语句：学习了在 if 或 else 代码块内部再嵌套 if 语句，实现更复杂的逻辑（如先判断是否为正数，再判断奇偶）。
取地址操作符：再次巩固了 scanf 中 & 的重要性（数组除外）。
️ 踩坑记录与注意事项
悬空 else 问题：
在嵌套 if 语句中，else 总是与离它最近的、未配对的 if 匹配，而不是根据缩进来判断。
建议：无论 if 或 else 后面有几行代码，都加上花括号 {}，这样可以明确代码块范围，避免逻辑错误。
== 与 = 的区别：
== 是判断相等，= 是赋值。在条件判断中如果误写成 =，会导致条件永远为真（非零值），且变量值被改变。
防御性写法：可以把常量写在左边，如 if (0 == a)，这样如果误写成 =，编译器会报错。
if 后面不要加分号：
if (条件); 这里的分号表示一个空语句，会导致 if 判断结束后什么都不做，后面的代码会无条件执行。
取地址操作符：
scanf 中除了数组名，其他变量都需要加 & 取地址，否则会导致程序崩溃或读取失败。				