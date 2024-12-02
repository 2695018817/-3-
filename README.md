实验三 分支结构程序设计
一、实验目的
1、了解 C 语言表示逻辑量的方法（以 0 代表“假”，以 1 代表“真”）。
2、学会正确使用逻辑运算符和逻辑表达式。
3、熟练掌握 if 语句和 switch 语句。
4、熟悉分支结构程序设计。
二、实验准备
1、复习关系、逻辑、条件运算符和表达式。
2、复习 if 语句的三种形式。
3、复习 if 语句的嵌套并能正确分析。
4、复习多分支选择 switch 语句。
三、实验内容
1、调试下列程序
#include <stdio.h>
void main()
{
	int a, b, max, min;
	scanf("%d%d", &a, &b);
	if (a > b) { max = a; min = b; }
	else { min = a; max = b; }
	printf("max=%d,min=%d\n", max, min);
	return 0;
}
问题：
•此程序的功能是什么？
这个程序的功能是比较两个整数的大小，输出打印这两个数中的最大值和最小值
•请用条件表达式语句（？：）修改程序使之完成相同的功能
#include <stdio.h>
int main() {
    int a, b, max, min;
    scanf("%d%d", &a, &b); 
    max = (a > b) ? a : b;
    min = (a > b) ? b : a;
    printf("max=%d, min=%d\n", max, min); 
    return 0; 
}
![VI7F@05I G}S}E3TY$ _(QV](https://github.com/user-attachments/assets/d55bdfaa-31ae-4313-badb-d348670a7944)
2、编程
（a）有一函数
用 scanf 函数输入 x 的值（分别为 x<1、1≤x<10、x≥10 三种情况），求 y 值。
#include <stdio.h>
int main() {
    double x, y;
    printf("请输入x的值：");
    scanf("%lf", &x);
    if (x < 1) {
        y = x;
    } else if (x < 10) {
        y = 2 * x - 1;
    } else {
        y = 3 * x - 11;
    }
    printf("%.4lf\n", y);
    return 0;
}
![ACEAC{WMDL@18~QFG_{(9%P](https://github.com/user-attachments/assets/2f3df909-910f-4609-b742-97ef8d637d42)
（b）给出一个百分制成绩，要求输出成绩等级‘A’‘B’‘C’‘D’‘E’。
（90 分以上为‘A’，81~89 分为‘B’，70~79 分为‘C’，60~69 分为‘D’，60 分以下为
‘E’。）
#include <stdio.h>

int main() {
    int score;
    char grade;
    scanf("%d", &score);
    if (score >= 90) {
        grade = 'A';
    } else if (score >= 81) {
        grade = 'B';
    } else if (score >= 70) {
        grade = 'C';
    } else if (score >= 60) {
        grade = 'D';
    } else {
        grade = 'E';
    }
    printf("%c\n", grade);
    return 0;
}
![%T%HO%RPSU9EN79 7%0KN6A](https://github.com/user-attachments/assets/a784e27b-638f-4f75-9da5-48a446c12b91)
（c）有一个不多于 5 位的正整数，要求：
•求出它是几位数。
•分别打印出每一位数字。
•按逆序打印出各位数字，例如原数为 321，应输出 123。
#include <stdio.h>
int main() {
    int num, reversed = 0, original, digit, count = 0;
    scanf_s("%d", &num);
    original = num;
    while (num != 0) {
        num /= 10;
        count++;
    }
    printf("这是一个%d位数。\n", count);
    printf("每一位数字分别为：");
    num = original;
    while (num != 0) {
        digit = num % 10;
        printf("%d ", digit);
        reversed = reversed * 10 + digit;
        num /= 10;
    }
    printf("\n逆序打印为：%d\n", reversed);
    return 0;
}
![Q}J4G0J7Y3KISONCCX( I](https://github.com/user-attachments/assets/f5c78fb2-f37a-4285-a92a-7970a2c710f5)
