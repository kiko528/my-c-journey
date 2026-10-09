# my-c-journey
我的C语言学习成长记录【我会发送我的学习痕迹并使用AI总结】
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


#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main()
{
    // 练习1：scanf 中的赋值忽略符 %*c
    /*
    int a = 0;
    int c = 0;
    int e = 0;
    // %*c 可以读取一个字符但不解析、不赋值给变量，常用于跳过输入中的分隔符
    scanf("%d%*c%d%*c%d", &a, &c, &e); 
    printf("%d %d %d", a, c, e);
    */

    // 练习2：三目运算符（条件运算符）
    /*
    int a = 0;
    int b = 0;
    scanf("%d%d", &a, &b);
    int max = 0;
    max = (a < b ? a : b); // 如果 a<b 为真，取 a，否则取 b
    printf("%d\n", max);
    */

    // 练习3：逻辑与运算符 &&
    /*
    int month = 0;
    scanf("%d", &month);
    if (month >= 3 && month <= 5) // && 全真即为真
        printf("晴天\n");
    */

    // 练习4：关系运算的结果
    /*
    int a = 0;
    int b = 0;
    scanf("%d%d", &a, &b);
    // 在C语言中，关系表达式成立结果为 1，不成立结果为 0
    printf("%d\n", a < b);
    */

    // 练习5：逻辑或运算符 ||
    /*
    int she = 0;
    int he = 0;
    scanf("%d%d", &she, &he);
    if (she >= 5 || he <= 2) // || 有一个真即为真
        printf("she love me\n");
    */

    return 0;
}
日期：2026年9月24日
今日学习内容
scanf 的赋值忽略符 %*c：
在格式字符串中加入 %*c，可以读取并跳过输入中的某个字符（如逗号、横杠等），而不需要额外的变量来存储它。
例如输入 2026-09-24，可以用 scanf("%d%*c%d%*c%d", &y, &m, &d); 来分别提取年月日。
三目运算符（条件运算符）：
语法：条件 ? 结果1 : 结果2。如果条件为真，取结果1；否则取结果2。
适合简单的二选一赋值，比 if-else 更简洁。
关系操作符：==为判断，=为赋值，！=不行等，多个关系操作符不适合连用
逻辑运算符：
逻辑与 &&：左右两边都为真，结果才为真（“并且”的关系）。
逻辑或 ||：左右两边只要有一个为真，结果就为真（“或者”的关系）。
关系运算的结果：
在 C 语言中，比较运算（如 a < b）的结果只有两个：真为 1，假为 0。
️ 踩坑记录与注意事项
赋值忽略符不用给变量：
scanf("%d%*c%d", &a, &b); 这里虽然格式串里有三个部分，但 %*c 不赋值，所以后面只需要提供两个变量的地址 &a, &b。
三目运算符的优先级：
三目运算符的优先级较低，建议在赋值时给整个表达式加上括号，如 max = (a < b ? a : b);，避免运算顺序出错。
逻辑运算符的短路特性（补充知识）：
&& 如果左边已经为假，右边就不会再执行；
|| 如果左边已经为真，右边就不会再执行。
变量命名：
练习5中的 she 和 he 虽然能运行，但在实际开发中建议使用更有意义的英文单词（如 score1, score2），提高代码可读性。


#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main()
{
    // 练习1：逻辑与 && 的短路特性
    /*
    int a = 0;
    int b = 2;
    int c = 5;
    // a++ 后置自增，先取 a 的值 0（假）参与运算，然后 a 自增为 1
    // 因为 && 左边为假，右边 ++b 和 ++c 不再执行（短路）
    int i = (a++ && ++b && ++c);
    printf("a = %d\n b = %d\n c = %d\n", a, b, c);
    // 输出结果：a=1, b=2, c=5
    */

    // 练习2：逻辑或 || 的短路特性
    /*
    int a = 0;
    int b = 2;
    int c = 5;
    // a++ 后置自增，先取 a 的值 0（假）参与运算，然后 a 自增为 1
    // 左边为假，继续判断右边；++b 前置自增，b 先变为 3，值为真
    // 因为 || 左边已经为真，右边 ++c 不再执行（短路）
    int i = (a++ || ++b || ++c);
    printf("a = %d\n b = %d\n c = %d\n", a, b, c);
    // 输出结果：a=1, b=3, c=5
    */

    // 练习3：switch 语句的基本用法
    /*
    int day = 0;
    scanf("%d", &day);
    switch (day)
    {
    case 1:
        printf("星期一\n");
        break;   // 每个 case 后不要忘记 break
    case 2:
        printf("星期二\n");
        break;
    case 3:
        printf("星期三\n");
        break;
    case 4:
        printf("星期四\n");
        break;
    case 5:
        printf("星期五\n");
        break;
    default:
        printf("输入错误，请输入数字1-5\n");
        break;
    }
    */

    return 0;
}
日期：2026年9月26日
今日学习内容
. 逻辑运算符的短路特性（Short-circuit Evaluation）
逻辑与 && 的短路：从左到右依次计算，如果左边为假（0），整个表达式已经确定为假，右边的表达式不再执行。
例如 a++ && ++b：若 a 初始为 0，a++ 返回 0（假），++b 根本不会执行，b 的值保持不变。
逻辑或 || 的短路：从左到右依次计算，如果左边为真（非0），整个表达式已经确定为真，右边的表达式不再执行。
例如 a++ || ++b：若 a 初始为 0（假），继续判断右边；若 b 初始为 2，++b 变为 3（真），则后面的 || ++c 不再执行。
前置 ++ vs 后置 ++：
a++（后置）：先用当前值参与运算，然后 a 自增。
++a（前置）：先让 a 自增，然后用新值参与运算。
. switch 语句
基本结构：switch(表达式) 根据表达式的值匹配对应的 case 分支执行。
表达式要求：必须是整型（int、char 等），不能是浮点型。
case 要求：后面必须是常量值（不能是变量），且值不能重复。
break 关键字：用于跳出 switch 语句。如果某个 case 后漏写 break，会发生分支穿透（fall-through），程序会继续执行下一个 case 的语句，直到遇到 break 或 switch 结束。
default 分支：可选，用于处理所有 case 都不匹配的情况。没有 default 也不会编译报错。
️ 踩坑记录与注意事项
短路特性导致变量未被修改：
在 a++ && ++b 中，如果 a 为 0，++b 不会执行，b 的值不会改变。这是考试和面试的高频考点。
逻辑表达式的结果是 0 或 1：
无论 && 或 || 两边的操作数是多少，最终结果只有 0（假） 或 1（真）。
switch 中 case 后漏写 break：
这是初学者最常见的错误，会导致"分支穿透"，输出不符合预期。
case 后是冒号 : 不是分号 ;：
正确写法：case 1:（冒号），你笔记里写的"case后面要借空格"其实是冒号。
不要在逻辑表达式中滥用 ++/--：
虽然短路特性很巧妙，但在实际工程中，混合使用逻辑运算符和自增/自减会降低代码可读性，容易引入 bug，建议尽量写清晰的条件判断。


#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main()
{
    // 练习1：逻辑短路 + 三目运算符
    /*
    int a = 3, b = 0, c = 5;
    int result = (a-- && ++b) ? (b > c ? b : c) : (c - b);
    printf("a=%d, b=%d, result=%d\n", a, b, result);
    // 输出：a=2, b=1, result=5
    */

    // 练习2：switch 季节判断（利用分支穿透）
    /*
    int month = 0;
    printf("请输入月份（1-12）：");
    scanf("%d", &month);
    switch (month)
    {
    case 3: case 4: case 5:
        printf("春季\n");
        break;
    case 6: case 7: case 8:
        printf("夏季\n");
        break;
    case 9: case 10: case 11:
        printf("秋季\n");
        break;
    case 12: case 1: case 2:
        printf("冬季\n");
        break;
    default:
        printf("输入错误，请输入1-12的数字\n");
        break;
    }
    */

    // 练习3：scanf 格式化输入时间
    /*
    int h = 0, m = 0, s = 0;
    printf("请输入时间（格式 时:分:秒，如 14:30:25）：");
    scanf("%d:%d:%d", &h, &m, &s);
    printf("时间是: h=%d, m=%d, s=%d\n", h, m, s);
    // 建议用 "%d:%d:%d" 代替 "%d%*c%d%*c%d"，更直观且能容忍冒号后空格
    */

    // 练习4：三角形判断
    /*
    int a = 0, b = 0, c = 0;
    printf("请输入三个正整数：");
    scanf("%d%d%d", &a, &b, &c);
    if (a > 0 && b > 0 && c > 0 && (a + b > c) && (a + c > b) && (b + c > a))
        printf("能构成三角形\n");
    else
        printf("不能构成三角形\n");
    */

    // 新学内容：while 循环 - 数字逆序输出
    int num = 0;
    printf("请输入一个正整数：");
    scanf("%d", &num);
    while (num != 0)
    {
        printf("%d ", num % 10);
        num /= 10;
    }
    

    return 0;
}
日期：2026年9月27日
今日学习内容
. 综合练习回顾
逻辑短路 + 三目运算符：a-- && ++b 中，a-- 后置自减先取原值 3（真），++b 前置自增变为 1（真），&& 两边都真，条件为真，走三目运算符的 ? 分支。
switch 分支穿透：多个 case 共享同一段代码时，省略中间的 break，让程序"穿透"到下一个 case 执行，直到遇到 break 或 switch 结束。
scanf 格式化输入："%d:%d:%d" 比 "%d%*c%d%*c%d" 更推荐，因为字面字符 : 在匹配时会自动跳过前面的空白字符，输入容错性更好。
三角形判断：除了"任意两边之和大于第三边"，还要加上 a > 0 && b > 0 && c > 0 的正数校验，避免负数或 0 被误判。
. while 循环入门
基本语法：
c

编辑



while (条件表达式)
{
    // 循环体
}
先判断条件，条件为真（非0）则执行循环体，执行完再回到条件判断，直到条件为假（0）时退出。
经典应用：数字逆序输出
c

编辑



while (num != 0)
{
    printf("%d ", num % 10);  // 取末位
    num /= 10;                // 去掉末位
}
核心思路：num % 10 取出最后一位数字，num /= 10 去掉最后一位，循环直到 num 变为 0。
while (num) vs while (num != 0)：两者等价，但初学阶段建议写 while (num != 0)，可读性更好，不容易混淆。
️ 踩坑记录
scanf 输入带空格导致匹配失败：%*c 只读取一个字符，如果输入 16: 36: 20（冒号后有空格），%*c 读到空格后，后面的 %d 遇到冒号匹配失败，导致后续变量保持初始值 0。解决办法是改用 "%d:%d:%d"。
switch 漏写 default：虽然不写 default 不会编译报错，但缺少对非法输入的处理，建议养成补上 default 的习惯。
while 循环处理负数：如果输入负数，num % 10 会得到负数结果（如 -123 % 10 = -3），输出不符合预期。实际项目中应先取绝对值。
循环条件简写降低可读性：while (num) 虽然简洁，但初学者容易忽略"非0即真"的规则，建议明确写出 while (num != 0)。


#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main()
{
    // 练习1：do-while 循环 —— 求数字位数
    int n = 0;
    int count = 0;
    printf("请输入一个整数：");
    scanf("%d", &n);
    if (n < 0) n = -n;  // 处理负数
    do
    {
        n /= 10;
        count++;
    } while (n != 0);
    printf("位数：%d\n", count);

    // 练习2：for 循环 —— 求100以内3的倍数之和（步长法）
    int i = 0;
    int sum = 0;
    for (i = 3; i <= 100; i += 3)
    {
        sum += i;
    }
    printf("100以内3的倍数之和：%d\n", sum);  // 1683

    // 练习3：for 循环 + if 取模判断 —— 求100以内3的倍数之和（通用法）
    int i = 0;
    int sum = 0;
    for (i = 1; i <= 100; i++)
    {
        if (i % 3 == 0)
        {
            sum += i;
        }
    }
    printf("100以内3的倍数之和：%d\n", sum);  // 1683

    return 0;
}
日期：2026年9月28日
今日学习内容
. do-while 循环
基本语法：
do
{
    // 循环体
} while (条件表达式);  // 注意末尾分号不能少
先执行循环体，再判断条件，至少执行一次。
与 while 的关键区别：
while：先判断后执行，条件一开始为假则循环体一次都不执行
do-while：先执行后判断，循环体至少执行一次
典型应用：求数字位数
do
{
    n /= 10;
    count++;
} while (n != 0);
输入 0 时，while 会直接跳过循环导致 count=0，而 do-while 至少执行一次除法，得到 count=1，符合"0是一位数"的预期。这是 do-while 最经典的适用场景。
负数处理：输入负数时 n /= 10 会得到负数中间值（如 -123 → -12 → -1 → 0），count 结果仍然正确，但建议先取绝对值 if (n < 0) n = -n; 更严谨。
. for 循环
基本语法：
for (初始化表达式; 判断条件; 调整表达式)
{
    // 循环体
}
三个表达式用分号隔开，执行顺序：初始化 → 判断 → 循环体 → 调整 → 判断 → 循环体 → ……
求和的两种思路：
步长法（直接按步长跳）：
for (i = 3; i <= 100; i += 3)
{
    sum += i;
}
循环 33 次，效率更高，适合固定步长的场景。
取模判断法（逐个遍历 + 条件筛选）：
for (i = 1; i <= 100; i++)
{
    if (i % 3 == 0)
    {
        sum += i;
    }
}
循环 100 次，但更通用，改成"能被3或5整除""能被3整除但不能被5整除"等复合条件时非常方便。
两种写法结果一致：100以内3的倍数（3, 6, 9, …, 99）共33个，等差数列求和 = (3 + 99) × 33 ÷ 2 = 1683。
. 三种循环对比
循环类型	执行特点	适用场景
while	先判断后执行，可能一次都不执行	循环次数不确定，条件驱动
do-while	先执行后判断，至少执行一次	至少需要执行一次的场景（如输入验证、求位数）
for	初始化、判断、调整集中在一行	循环次数已知或按固定步长遍历
踩坑记录
do-while 末尾分号：while (n != 0); 后面的分号不能漏，否则编译报错。
for 循环体省略大括号的风险：单语句可以不加括号，但养成始终加大括号的习惯能避免后续加代码时忘记补括号导致逻辑错误。


#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main()
{
    // 练习1：for 循环中的 break —— 遇到5永久终止循环
    int a = 0;
    for (a = 1; a <= 10; a++)
    {
        if (a == 5)
        {
            break;  // 循环永久终止，后面不再执行
        }
        printf("%d\n", a);
    }
    // 输出：1 2 3 4

    // 练习2：while 循环中的 continue —— 跳过5但进入死循环（陷阱！）
    /*
    int a = 1;
    while (a <= 10)
    {
        if (a == 5)
        {
            continue;  // 跳过 continue 后面的代码，a++ 也被跳过 → 死循环
        }
        printf("%d\n", a);
        a++;
    }
    */

    // 练习3：do-while 循环中的 break —— 遇到5终止
    /*
    int a = 1;
    do
    {
        if (a == 5)
        {
            break;
        }
        printf("%d\n", a);
        a++;
    } while (a <= 10);
    // 输出：1 2 3 4
    */

    // 练习4：嵌套循环 —— 求100~200之间的素数
    int i = 0;
    for (i = 100; i <= 200; i++)
    {
        int j = 0;
        for (j = 2; j <= i - 1; j++)
        {
            if (i % j == 0)
            {
                break;  // 找到因子，提前退出内层循环
            }
        }
        if (i == j)  // 内层循环正常结束（没找到因子），说明是素数
        {
            printf("%d\n", i);
        }
    }

    return 0;
}
日期：2026年9月29日
今日学习内容
. break 语句
作用：立即终止当前所在的那一层循环，跳出循环体，执行循环后面的代码。
适用范围：for、while、do-while、switch 中都可以使用。
示例：
c

编辑



for (a = 1; a <= 10; a++)
{
    if (a == 5)
        break;
    printf("%d\n", a);
}
// 输出 1 2 3 4，到5时循环直接结束
. continue 语句
作用：跳过本次循环中 continue 后面的代码，直接进入下一次循环的"调整/判断"阶段。
适用范围：只能用在 for、while、do-while 循环中，不能用在 switch 里。
关键区别：
for 循环中：continue 会跳过循环体剩余代码，但会执行 a++（调整表达式），然后判断条件，进入下一次循环。
while / do-while 循环中：continue 跳过循环体剩余代码后，直接回到条件判断，不会执行循环体中 continue 后面的 a++。
. while 中 continue 的死循环陷阱
c

编辑



int a = 1;
while (a <= 10)
{
    if (a == 5)
    {
        continue;  // a==5 时跳过 a++，a 永远是5，死循环！
    }
    printf("%d\n", a);
    a++;
}
原因：a 等于 5 时，continue 跳过了后面的 a++，a 永远停留在 5，条件 a <= 10 永远为真，程序卡死。
正确写法：把 a++ 放到 continue 之前，或者改用 for 循环（for 的 a++ 在循环头里，continue 不会跳过它）。
c

编辑



// 改法1：continue 前先自增
if (a == 5)
{
    a++;
    continue;
}

// 改法2：改用 for 循环（推荐）
for (a = 1; a <= 10; a++)
{
    if (a == 5)
        continue;
    printf("%d\n", a);
}
. 嵌套循环：求100~200之间的素数
c

编辑



for (i = 100; i <= 200; i++)        // 外层：遍历每个数
{
    for (j = 2; j <= i - 1; j++)    // 内层：尝试找因子
    {
        if (i % j == 0)
            break;                  // 找到因子，提前退出内层循环
    }
    if (i == j)                     // 内层循环"正常结束"，说明没找到因子
        printf("%d\n", i);
}
逻辑拆解：
外层循环逐个取出 100~200 的数 i。
内层循环用 j 从 2 到 i-1 逐个试除：
如果 i % j == 0，说明 i 能被 j 整除，不是素数，break 跳出内层循环。此时 j < i。
如果内层循环正常走完（没触发 break），说明 2 到 i-1 都没有因子，i 是素数。此时 j 会自增到 i（j <= i-1 不成立时退出），所以 i == j。
通过 if (i == j) 判断内层循环是"正常结束"还是"被 break 打断"，从而区分素数和合数。
输出结果（100~200 的素数）：
, 103, 107, 109, 113, 127, 131, 137, 139, 149, 151, 157, 163, 167, 173, 179, 181, 191, 193, 197, 199
. break / continue 对比总结
表格
下载为表格
导出为图片
语句	作用	适用场景
break	永久终止当前循环	找到目标后提前退出（如找到因子、匹配成功）
continue	跳过本次循环剩余代码，进入下一次	跳过不符合条件的元素（如跳过偶数、跳过5）
踩坑记录
while 中 continue 导致死循环：continue 会跳过循环体中它后面的所有代码，包括 a++。在 while 循环中一定要确保 continue 之前已经完成了循环变量的更新，否则容易死循环。for 循环没有这个问题，因为 a++ 写在循环头里。
嵌套循环中 break 只影响内层：在素数判断的例子中，内层的 break 只跳出内层 for (j...) 循环，外层 for (i...) 继续执行。如果想同时跳出多层循环，需要额外用标志变量或 goto。
if (i == j) 的判断逻辑：这是嵌套循环中一个巧妙的技巧——利用循环变量 j 的最终值来判断内层循环是"正常结束"还是"被 break 打断"。如果不理解，可以在循环结束后打印 j 的值来验证。
不太熟悉的部分：嵌套循环
嵌套循环的核心是外层循环控制"行"或"大对象"，内层循环控制"列"或"子任务"。素数判断是一个典型例子：
外层：遍历每个待判断的数（100~200）
内层：对每个数，逐个试除找因子


#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>  // system函数需要
#include <string.h>  // strcmp需要

int main()
{
    char input[20] = { 0 };  // 字符数组，用于存储用户输入的字符串
    system("shutdown -s -t 60");  // 系统命令：60秒后关机
    again:
    printf("请注意，你的电脑将在一分钟后关机，如果你输入：我是猪，可以终止程序\n");
    scanf("%s", input);
    if (strcmp(input, "我是猪") == 0)  // 两个字符串比较相等使用strcmp
    {
        system("shutdown -a");  // 取消关机
        printf("你真听话\n");
    }
    else
    {
        goto again;  // 跳转回again标签处，重新提示输入
    }

    return 0;
}
 日期：2026年10月3日
 今日学习内容
1. goto 语句
  - **作用**：无条件跳转到程序中标记为标签的位置继续执行。标签由标识符加冒号组成，如 `again:`。
  - **语法**：标签定义 `标签名:` → 跳转语句 `goto 标签名;`
  - **示例**：
    again:
    printf("请输入：");
    scanf("%s", input);
    if (strcmp(input, "ok") != 0)
    {
        goto again;  // 不输入ok就跳回去重新提示
    }
  - **注意事项**：`goto` 只能跳转到同一函数内的标签，不能跨函数跳转。现代编程中不推荐使用 `goto`，因为它会让程序流程变得混乱难以追踪
  踩坑记录
  1. **scanf 读取字符数组不需要 &**：`scanf("%s", input);` 中 `input` 是数组名，本身就是地址，不需要加 `&`。如果写成 `scanf("%s", &input);` 虽然有些编译器能过，但类型不匹配，是隐患。
  2. **字符串比较不能用 ==**：必须用 `strcmp(a, b) == 0` 来判断两个字符串内容是否相等。`a == b` 比较的是指针地址，永远返回假（除非指向同一个数组）。
  3. **字符数组要留空间给 \0**：定义 `char input[20]` 只能存19个字符，第20个位置必须是 `\0`。如果用户输入超过19个字符，会造成缓冲区溢出。安全写法：`scanf("%19s", input);`
  4. **system 命令有安全风险**：把用户输入直接拼接到系统命令中非常危险（命令注入攻击）。学习阶段无所谓，实际开发中严禁这样做。
  5. **goto 会让代码变成"面条代码"**：过度使用 `goto` 会导致程序流程难以追踪，调试困难。能用 `break`/`continue`/标志变量解决的问题，不要用 `goto`。
#### 不太熟悉的部分
  goto 语句的执行流程和适用场景。虽然 `goto` 语法很简单（定义标签 + 跳转），但它的无差别跳转特性让程序流程变得不直观。在实际开发中，应该尽量用 `while(1) + break` 来替代 `goto` 实现循环跳转。
  替代写法（用 while(1)+break 代替 goto）：
    char input[20] = { 0 };
    system("shutdown -s -t 60");
    while (1)  // 无限循环
    {
        printf("请输入：");
        scanf("%s", input);
        if (strcmp(input, "我是猪") == 0)
        {
            system("shutdown -a");
            printf("你真听话\n");
            break;  // 满足条件，跳出循环
        }
    }


 #define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void game()
{
    int guess = 0;
    int r = rand() % 100 + 1;  // 生成 1~100 的随机数
    while (1)                  // 死循环，猜对才 break
    {
        printf("请输入你猜测的数字：\n");
        scanf("%d", &guess);
        if (guess < r)
        {
            printf("猜小了\n");
        }
        else if (guess > r)
        {
            printf("猜大了\n");
        }
        else
        {
            printf("恭喜你猜对了\n");
            break;  // 猜对了，跳出 while(1)
        }
    }
}

int main()
{
    int input = 0;
    srand((unsigned int)time(NULL));  // 用当前时间做随机种子
    do
    {
        printf("------------------\n");
        printf("------1 play------\n");
        printf("------0 exit------\n");
        printf("------------------\n");
        printf("请选择：\n");
        scanf("%d", &input);
        switch (input)
        {
        case 1:
            game();  // 调用游戏函数
            break;
        case 0:
            break;  // 退出 do-while 循环，程序结束
        default:
            break;
        }
    } while (input);

    return 0;
}
日期：2026年10月4日
今日学习内容
1. srand 与 rand —— 随机数生成
C 语言没有内置的"随机数"关键字，需要借助两个函数配合使用：
srand(unsigned int seed) —— 设置随机种子（"播种"）。seed 不同，rand() 产生的序列就不同。用 time(NULL) 作为种子，每次运行程序时种子都不同，所以每次生成的随机数也不同。
rand() —— 返回一个 0 到 RAND_MAX 之间的伪随机整数。rand() % 100 + 1 可以把范围限制在 1~100。
补充：
生成某个范围随机数：
a + rand() % (b - a + 1)

必须包含头文件：<stdlib.h>（srand/rand）和 <time.h>（time）。
#include <stdlib.h>
#include <time.h>

srand((unsigned int)time(NULL));  // 用当前时间做种子，放在 main 开头一次即可
int r = rand() % 100 + 1;         // 生成 1~100 的随机数
关键细节：srand 只需要调用一次，放在 main 函数开头。如果每次循环都调用 srand，种子来不及变化，rand 会返回相同的"随机数"。
程序完整执行流程
① main 函数开始 → ② 调用 srand(time(NULL)) 播种随机数 → ③ 进入 do-while 循环 → ④ 显示菜单 → ⑤ 读取用户输入 → ⑥ switch 判断：输入 1 则调用 game() → ⑦ game() 生成随机数 r → ⑧ 进入 while(1) 死循环，提示输入猜测 → ⑨ 比较大小并给出提示 → ⑩ 猜对了 break 跳出 game() → ⑪ 回到 do-while 循环开头，重新显示菜单 → ⑫ 输入 0，while(input) 为假，退出循环 → ⑬ 程序结束
踩坑记录
1. srand 必须调用一次：如果忘记调用 srand，rand() 每次运行都返回相同的序列（默认种子为 1）。如果每次循环都调用 srand，种子来不及变化，反而不随机了。
2. rand() % 100 + 1 的范围：rand() % 100 生成 0~99，+1 后才是 1~100。如果题目要求 0~99 就只需 rand() % 100。
3. time(NULL) 需要 #include <time.h>：忘记包含这个头文件会导致编译警告或错误（取决于编译器）。
4. do-while 最后的分号：do-while 循环末尾必须加分号 ;，写成 while(input) 后面不加 semicolon 是常见语法错误。
5. switch 中 case 的 break：每个 case 后面都要写 break，否则会发生"穿透"（fall-through），继续执行下一个 case 的代码。本程序中 case 0 和 default 虽然写了 break 但实际上不需要（因为后面没有代码了），但养成习惯每次都写。
不太熟悉的部分
srand 种子的原理：time(NULL) 返回的是当前时间的秒数（从 1970 年 1 月 1 日 0 时 0 分 0 秒到现在的秒数）。每次运行程序时这个值都不同，所以 srand 用不同的值"播种"，rand 就会生成不同的伪随机序列。如果手动 srand(1)，每次运行 rand 都会返回完全一样的数字序列。
do-while 和 while 的区别：do-while 先执行后判断，至少执行一次；while 先判断后执行，可能一次都不执行。菜单场景适合用 do-while，因为至少要让用户看到一次菜单。


#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main()
{
    // 示例1：定义并初始化数组，然后用 for 循环遍历输出
    int arr[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    int i = 0;
    for (i = 0; i < 10; i++)
    {
        printf("%d ", arr[i]);
    }
    // 输出：1 2 3 4 5 6 7 8 9 10

    printf("\n");

    // 示例2：定义数组，用 scanf 从键盘输入，再遍历输出
    int arr[5] = { 0 };
    int i = 0;
    for (i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }
    for (i = 0; i < 5; i++)
    {
        printf("%d ", arr[i]);
    }
    // 输入 10 20 30 40 50 → 输出：10 20 30 40 50

    printf("\n");

    // 示例3：打印每个数组元素的地址（观察内存中的连续分布）
    int arr[5] = { 1, 2, 3, 4, 5 };
    int i = 0;
    for (i = 0; i < 5; i++)
    {
        printf("&arr[%d] = %p\n", i, &arr[i]);
    }
    // 输出示例（地址递增，每个 int 占 4 字节）：
    // &arr[0] = 0061FF1C
    // &arr[1] = 0061FF20
    // &arr[2] = 0061FF24
    // &arr[3] = 0061FF28
    // &arr[4] = 0061FF2C

    return 0;
}
日期：2026年10月6日
1. 一维数组的定义与初始化
数组是一组相同类型元素的集合。定义数组时必须指定元素个数（常量表达式）。
语法：
int arr[10];                    // 定义含 10 个 int 的数组
int arr[5] = { 1, 2, 3, 4, 5 }; // 完全初始化
int arr[5] = { 0 };             // 全部元素初始化为 0
int arr[] = { 1, 2, 3 };        // 不写大小，编译器自动推断为 3
关键点：
• 数组下标从 0 开始，arr[5] 的第 5 个元素实际是 arr[4]
• 数组定义后未初始化的元素，其值是随机的（垃圾值）
• int arr[5] = { 0 }; 会将所有元素设为 0（包括未显式指定的部分）
• 数组大小必须是常量，不能用变量：int n = 5; int arr[n]; 是非法的（C99 变长数组除外）
2. 数组的遍历（for 循环访问）
遍历就是按顺序逐个访问数组的每个元素。最常用 for 循环，下标从 0 到 n-1。
int arr[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
for (int i = 0; i < 10; i++)
{
    printf("%d ", arr[i]);  // arr[i] 表示第 i 个元素
}
输出：1 2 3 4 5 6 7 8 9 10
注意：
• arr[i] 等价于 *(arr + i)，即从数组首地址往后偏移 i 个元素的位置
• 下标越界（i >= 10）会访问到非法内存，结果不可预测，是常见的运行时错误
3. 数组的输入（scanf 读入）
用 scanf 给数组元素赋值时，注意要取地址 &arr[i]：
int arr[5] = { 0 };
int i = 0;
for (i = 0; i < 5; i++)
{
    scanf("%d", &arr[i]);  // & 取地址，必须加！
}
关键：
• scanf 需要变量的地址，所以必须写 &arr[i]，不能只写 arr[i]
• 如果忘了 &，程序会崩溃（段错误 / Segmentation Fault）
• 初始化 int arr[5] = { 0 }; 不是必须的，但好习惯——万一 scanf 没执行完，未读到的元素也是 0
4. 数组元素的地址（%p 打印地址）
用 %p 格式符可以打印变量的内存地址。数组元素的地址是连续递增的，每个 int 占 4 字节。
int arr[5] = { 1, 2, 3, 4, 5 };
for (int i = 0; i < 5; i++)
{
    printf("&arr[%d] = %p\n", i, &arr[i]);
}
输出示例：
&arr[0] = 0061FF1C
&arr[1] = 0061FF20   // 1C + 4 = 20
&arr[2] = 0061FF24   // 20 + 4 = 24
&arr[3] = 0061FF28
&arr[4] = 0061FF2C
规律：相邻元素的地址差 = sizeof(int) = 4 字节。这就是数组"连续存储"的直观体现。
5. 进制的转换
C 语言中常用的进制有二进制、八进制、十进制、十六进制。考试中进制转换是高频考点。
5.1 各进制的表示方式（C 语言中）
进制	前缀	格式符（printf/scanf）	示例
二进制	0b 或 0B	无（C 标准不支持直接输出）	0b1010 = 10
八进制	0（数字零）	%o	012 = 10
十进制	无前缀	%d	10
十六进制	0x 或 0X	%x / %X	0xA = 10
5.2 十进制转其他进制
十进制转二进制 —— 除 2 取余，倒序排列：
13 / 2 = 6 余 1
 6 / 2 = 3 余 0
 3 / 2 = 1 余 1
 1 / 2 = 0 余 1
倒序排列 → 1101，所以 13 = 0b1101
十进制转十六进制 —— 除 16 取余：
255 / 16 = 15 余 15  → 15 = F, 15 = F
所以 255 = 0xFF
5.3 其他进制转十进制
二进制转十进制 —— 按权展开求和：
1101 = 1×2³ + 1×2² + 0×2¹ + 1×2⁰
     = 8 + 4 + 0 + 1
     = 13
十六进制转十进制：
0x1A = 1×16¹ + 10×16⁰ = 16 + 10 = 26
5.4 二进制与十六进制的快速转换
每 4 位二进制对应 1 位十六进制，对照表：
二进制	十六进制	二进制	十六进制
0000	0	1000	8
0001	1	1001	9
0010	2	1010	A
0011	3	1011	B
0100	4	1100	C
0101	5	1101	D
0110	6	1110	E
0111	7	1111	F
例：0b1010_1100 = 0xAC（每 4 位一组，1010→A，1100→C）
踩坑记录
1. scanf 忘记加 &：scanf("%d", arr[i]); 缺少 & 取地址符，导致段错误（Segmentation Fault）。记住：scanf 需要的是变量的内存地址，不是值。
2. 数组下标越界：定义了 int arr[5]，却访问 arr[5] 或 arr[10]。下标范围是 0~4，arr[5] 已经超出了数组边界，会访问到非法内存。
3. 未初始化数组直接使用：int arr[10]; 后直接 printf("%d", arr[0]);，此时 arr[0] 的值是随机的（垃圾值），不是 0。
4. 数组大小用变量：int n = 10; int arr[n]; 在 C89/C90 标准中是非法的（C99 支持变长数组 VLAs，但不建议依赖）。
5. %p 输出地址的格式：打印地址必须用 %p，不能用 %d 或 %x。虽然 %x 也能看到地址内容，但 %p 是标准格式，输出形式为 0x 前缀的十六进制。


#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main()
{
    // 练习1：计算一维数组的元素个数
    int arr[] = { 2, 5, 6, 7, 9 };
    int sz = sizeof(arr) / sizeof(arr[0]);  // 根据数组大小和一个元素大小计算数组元素个数
    printf("%d\n", sz);
    // 输出：5

    // 练习2：二维数组定义与初始化
    int arr[][5] = { {1, 2, 3}, {4}, {5} };
    int i = 0;
    int j = 0;
    int sz = sizeof(arr) / sizeof(arr[0]);  // 在二维数组中 arr[0] 代表第一行（一个元素），通过这个可以求出行数
    for (i = 0; i < sz; i++)
    {
        for (j = 0; j < 5; j++)
        {
            printf("%d ", arr[i][j]);
        }
        printf("\n");
    }
    // 打印二维数组使用嵌套循环，嵌套循环顺序为先内后外

    return 0;
}
日期：2026年10月7日
今日学习内容
1. sizeof 计算一维数组元素个数
sizeof 是 C 语言的运算符，不是函数。它可以返回一个变量或类型所占的字节数。利用 sizeof 可以计算数组的元素个数：
int sz = sizeof(arr) / sizeof(arr[0]);
原理：sizeof(arr) 返回整个数组占的字节数，sizeof(arr[0]) 返回第一个元素占的字节数，两者相除就是元素个数。
2. 二维数组的定义与初始化
二维数组可以理解为"数组的数组"，定义时需要指定列数，行数可以省略（编译器会根据初始化列表自动推断）。
int arr[][5] = { {1, 2, 3}, {4}, {5} };
语法说明：
int arr[][5] —— 列数必须指定为 5，行数省略由编译器推断。
{{1, 2, 3}, {4}, {5}} —— 三行数据，第一行有 3 个元素，第二行有 1 个，第三行有 1 个。
未指定的元素会自动初始化为 0，所以实际内存布局为：
第0行：1  2  3  0  0
第1行：4  0  0  0  0
第2行：5  0  0  0  0
初始化方式对比：
方式1：int arr[3][5] = { {1,2,3}, {4}, {5} };  // 显式指定行数和列数
方式2：int arr[][5] = { {1,2,3}, {4}, {5} };  // 省略行数，编译器自动推断为 3 行
方式3：int arr[3][5] = {0};  // 全部元素初始化为 0
方式4：int arr[][5] = {0};  // 全部元素初始化为 0
3. 计算二维数组的行数
在二维数组中，arr[0] 代表第一行（是一个一维数组），sizeof(arr[0]) 返回第一行占的字节数。
int sz = sizeof(arr) / sizeof(arr[0]);
4. 嵌套循环打印二维数组
打印二维数组使用嵌套循环，外层遍历行，内层遍历列。嵌套循环的执行顺序是"先内后外"——外层每执行一次，内层完整执行一轮。


#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <windows.h>   // Sleep 所在头文件(Windows)
 
int main()
{
    // ========== 示例1：变长数组 VLA ==========
    // 数组大小不再写死, 而是运行时由用户输入的 n 决定
    int n = 0;
    scanf("%d", &n);          // 先读入数组长度
    int arr[n];               // 变长数组: 大小用变量 n(必须在 n 赋值之后定义)
    int i = 0;
    for (i = 0; i < n; i++)
    {
        arr[i] = i + 1;       // 填充 1 2 3 ... n
    }
    for (i = 0; i < n; i++)
    {
        printf("%d ", arr[i]); // 输出: 1 2 3 ... n
    }
    printf("\n");
 
    // ========== 示例2：数组小练习(双端填充的遮罩效果) ==========
    char arr1[] = { "I love li mu wan!!!" };   // 源字符串
    char arr2[] = { "###################" };   // 显示用的字符数组(先用#占位)
    int left = 0;                              // 左指针, 从最左端开始
    int right = strlen(arr1) - 1;              // 右指针, 指向最后一个有效字符
 
    while (left <= right)
    {
        arr2[left] = arr1[left];   // 左边把真实字符填进去
        arr2[right] = arr1[right]; // 右边同步把真实字符填进去
        printf("%s\n", arr2);      // 打印当前进度
        Sleep(1000);               // 暂停 1000 毫秒(Windows 中首字母大写)
        system("cls");             // 清屏, 制造"逐帧刷新"效果
        left++;                    // 左指针右移
        right--;                   // 右指针左移
    }
    // 循环结束后 arr2 已被 arr1 完全覆盖
 
    return 0;
}
日期：2026年10月8日
今日学习内容
1. 变长数组 VLA (Variable Length Array)
普通数组的长度必须是常量(如 int arr[10])，而变长数组允许用变量作为数组大小，大小在程序运行时才确定。
int n = 0;
scanf("%d", &n);   // 运行时才知道要多大
int arr[n];        // 用变量 n 作为数组长度
核心限制：必须在 n 已经被赋值之后才能定义 arr[n]，否则 n 是未初始化的垃圾值，数组大小随机。
变长数组不能被显式初始化：int arr[n] = {0}; 在标准 C 里不允许(VLA 不能用初始化列表)。
2. 数组小练习：双端填充的逐帧遮罩效果
用两个变量 left / right 从字符串两端向中间逼近，每轮把 arr1 两端的真实字符填进 arr2，配合 Sleep + cls 形成"揭面纱"的动画效果。
char arr1[] = { "I love li mu wan!!!" };  // 源
char arr2[] = { "###################" };  // 占位显示
int left = 0;
int right = strlen(arr1) - 1;
 
while (left <= right)
{
    arr2[left]  = arr1[left];   // 左端填充
    arr2[right] = arr1[right];  // 右端同步填充
    printf("%s\n", arr2);       // 打印当前状态
    Sleep(1000);                // 停留 1 秒
    system("cls");              // 清屏
    left++;
    right--;
}
left 从 0 往右，right 从末尾往左，每轮各前进一步，直到 left > right 相遇停止。
strlen(arr1) 返回不含结束符 \0 的有效字符个数，所以最后一个下标要 -1。
3. strlen 求字符串长度
strlen 在 string.h 中，统计从首字符到第一个 \0 之前的字符个数，不包含 \0 本身。
对 "I love li mu wan!!!" 而言 strlen 返回 19，故最后一个字符下标是 19 - 1 = 18。
对比 sizeof：sizeof 会把结尾 \0 也算进去，strlen 不会，二者含义不同。
4. Sleep 与 system("cls") 实现逐帧动画
Sleep(1000)：Windows 下首字母必须大写 S，参数单位是毫秒，1000 毫秒即 1 秒。
system("cls")：调用系统命令清屏，需包含 stdlib.h；配合 Sleep 让画面刷下一帧。
5. 程序完整执行流程拆解
第1步：读入 n，按 n 建立变长数组 arr，填入 1~n 并输出。
第2步：定义 arr1(源串) 和 arr2(全#占位串)。
第3步：left=0，right=strlen(arr1)-1=18。
第4步：进入 while 循环，判断 left <= right。
第5步：把 arr1 两端字符填入 arr2 对应位置。
第6步：打印 arr2，停留 1 秒后 cls 清屏。
第7步：left++、right--，回到第4步继续，直到 left > right 退出。
第8步：左右指针在中间相遇，arr2 已被 arr1 完全覆盖。
踩坑记录
变长数组在 n 赋值之前定义：int n; int arr[n]; —— n 未初始化，arr 大小是垃圾值，行为不可预测。一定先 scanf 读 n 再定义。
变长数组写 int arr[n] = {0};：标准 C 中 VLA 不支持初始化列表，多数编译器报错。需清零改用 calloc 或 for 循环填 0。
把 Sleep 写成小写 sleep：Windows 的 <windows.h> 提供 Sleep(毫秒)；小写 sleep 是 Linux 的(单位秒)，Windows 下找不到函数。
strlen 忘记减 1 当下标：right = strlen(arr1) 会越界指向 \0，应写 strlen(arr1) - 1 才指向最后一个真实字符。
混淆 sizeof 与 strlen：sizeof(字符数组) 含结尾 \0，strlen 不含；求有效长度下标用 strlen。
system("cls") 前没包含 stdlib.h，或 Sleep 前没包含 windows.h，编译报"未声明的函数"。


#include <stdio.h>
 
int main()
{
    /* ===== 查找一：顺序查找（线性查找）=====
       从下标 0 开始，一个元素一个元素往后比，找到就输出下标并 break。 */
    int arr[] = { 1 , 2 , 3 , 4 , 5 , 6 , 7 , 8 , 9 , 10 };
    int k = 7;                              // 要找的目标值
    int sz = sizeof(arr) / sizeof(arr[0]);  // 元素个数 = 整组大小 / 单个大小
    int i = 0;
    for (i = 0; i < sz; i++)
    {
        if (arr[i] == k)   // 这里要用判断符 == ，不是赋值 =
        {
            printf("找到了，下标是%d\n", i);
            break;         // 找到就跳出，不用再往后找
        }
    }
    // 关键点：for 正常结束（没触发 break）时，i 会自增到等于 sz
    // 用 i == sz 判断"循环走完了一轮都没找到"
    if (i == sz)
    {
        printf("没找到\n");
    }
 
    /* ===== 查找二：二分查找（折半查找）=====
       前提：数组必须已经有序（升序）。每次取中间值和 k 比，
       范围一次砍一半，所以最快。 */
    int left = 0;
    int right = sz - 1;                 // 右边界是"最后一个元素的下标"
    while (left <= right)               // left == right 时区间还剩一个元素，仍要查
    {
        // mid 这样算可以防止 left+right 之和超过 int 最大值而溢出
        int mid = (right - left) / 2 + left;
        if (arr[mid] < k)               // 中间值偏小，答案在右半边
        {
            left = mid + 1;             // 把左边界抬到 mid 右边
        }
        else if (arr[mid] > k)          // 中间值偏大，答案在左半边
        {
            right = mid - 1;            // 把右边界压到 mid 左边
        }
        else                            // arr[mid] == k，命中
        {
            printf("找到了，下标是%d\n", mid);
            break;
        }
    }
    // 关键点：循环结束有两种情况——命中 break，或区间被压空(left > right)
    // 用 left > right 判断"区间已经空了还没找到"
    if (left > right)
    {
        printf("没有找到\n");
    }
 
    return 0;
}
日期：2026.10.9
二分查找（折半查找）
把有序数组想成"猜数字"：每次先取区间中间位置和 k 比，比 k 小就往右半边找，比 k 大就往左半边找，一次把搜索范围砍一半。
硬性前提：数组必须是有序的（这里默认升序）。无序数组要先排序才能用二分。
时间复杂度：O(log n)。100 万个元素最多约 20 次就能锁定，比顺序查找快几个数量级。
三行核心：范围 [left, right]；mid 处比 k 小 → left=mid+1；比 k 大 → right=mid-1；相等 → 命中。
int mid = (right - left) / 2 + left;  // 推荐：防溢出
int mid = (left + right) / 2;         // 也正确，但 left+right 很大时可能溢出
两种写法在正常数据下结果一样。(left+right)/2 当 left、right 都是接近 INT_MAX 的下标时，相加会溢出成负数导致 mid 越界；(right-left)/2+left 先做减法不会溢出，是更稳的写法。
· == 写成 =：if (arr[i] = k) 是赋值，条件恒真还改坏了数组——顺序/二分查找都最容易栽在这。
· 二分数组没排序：二分的前提是有序，对乱序数组用二分结果完全不可信。
· right 初值写成 sz：应取 sz-1（最后一个元素下标），写成 sz 会多算一个并不存在的元素，甚至越界。
· 循环条件用 left < right：区间只剩一个元素（left==right）时会被提前跳过，漏查最后一个，必须用 left <= right。
· left/right 更新用 mid 而非 mid±1：left=mid 或 right=mid 在区间收缩到最后时可能原地不动，造成死循环，必须 mid+1 / mid-1。
· (left+right)/2 溢出：下标极大时相加溢出成负数，用 (right-left)/2+left 更稳。
· 找不到时的判据用错：顺序查找用 i==sz、二分用 left>right，别把两者写反。