# 基础

## 入门

### 简介

```
结构化语言
它产生高效率的程序
```

### 安装

```
visual studio
qt
mingw + notepad++
```

### 二进制

```
二进制 1111 1111
十进制 255
八进制 377
16进制 0xFF
```

原码
反码 负数,符号位不变，数值位取反
补码: 负数反码+1；

正数: 三位一体,都与原码相同
负数：按照规则转码

```
原码 0010 0110
反码 0010 0110
补码 0010 0110

原码 1010 0110
反码 1101 1001
补码 1101 1010
```

### hello world

```c
#include <stdio.h>
int main(int argc, char *argv[])
{
    printf("%s\n","hello world");
    return 0;
}
```

```
预处理器指令
函数
变量
语句 & 表达式
注释
```

### 编译运行

### 调试

```
继续
单步跳过 ： 执行本函数的下一步
单步进入 : 执行下一步
单步跳出 : 返回上节点的函数内
```



### 关键字

**1)非常见：**auto、register、volatile、goto
**2)存储相关：**const、extern、register、volatile、static、auto、signed、unsigned
**3)数据类型：**char、short、int、float、long、double、struct、union、enum、void
**4)逻辑控制：**if、else、for、while、do、break、continue、return、default、switch、case、goto
**5)特殊用途：**sizeof、typedef

32 个;

```
auto ：声明自动变量
short ：声明短整型变量或函数 　　
int： 声明整型变量或函数
long ：声明长整型变量或函数 　　
float：声明浮点型变量或函数 　　
double ：声明双精度变量或函数 　　
char ：声明字符型变量或函数 　　
struct：声明结构体变量或函数 　　
union：声明共用数据类型 　　
enum ：声明枚举类型 　　
typedef：用以给数据类型取别名 　　
const ：声明只读变量 　　
unsigned：声明无符号类型变量或函数 　　
signed：声明有符号类型变量或函数 　　
extern：声明变量是在其他文件正声明 　　
register：声明寄存器变量 　　
static ：声明静态变量 　　
volatile：说明变量在程序执行中可被隐含地改变 　　
void ：声明函数无返回值或无参数，声明无类型指针 　　
if:条件语句 　　
else ：条件语句否定分支（与 if 连用） 　　
switch :用于开关语句 　　case：开关语句分支 　　
for：一种循环语句 　　
do ：循环语句的循环体 　　
while ：循环语句的循环条件 　　
goto：无条件跳转语句 　　
continue：结束当前循环，开始下一轮循环 　　
break：跳出当前循环 　　
default：开关语句中的“其他”分支 　　
sizeof：计算数据类型长度 　　
return ：子程序返回语句（可以带参数，也可不带参数）循环条件
```



## 表达式

### 标识符

```c
    必须由字母（区分大小写）、数字、下划线组成。而且，标识符的第一个字符不可以是数字， 
    标识符是C语言最基础的组成部分。 
    关键字  数据类型  变量 函数 等的命名都是要符号标识符规则
```

### 注释

```
// 单行注释
/* */ 多行注释
```

### 数据类型

```
本质: 占用固定字节数的内存模型 模板
三要素: 大小、名称、作用域
别名 typedef
作用是 定义变量 
```

**基本数据类型**

```
int       : 占据的内度存大小是2 个byte
short int : 占据的内度存大小是4 个byte
long int  : 占据的内度存大小是4 个byte
char      : 占据的内度存大小是1 个byte
float     : 占据的内度存大小是4 个byte
double    : 占据的内度存大小是8 个byte
```

**修饰词**

```
signed、unsigned  有符号和无符号
```

**复合数据类型**

```
struct 结构体
union 联合
enum 枚举
数组  []
指针 * &
```

**其他类型**

```
void
函数类型
```

### 字面量

对固定值的标识，可用于对变量赋值

整数

```
二进制: 0b
十进制:  1 22
八进制: 0123
16进制: 0x1234
前缀指定基数：0x 或 0X 表示十六进制，0 表示八进制，不带前缀则默认表示十进制。
整数常量也可以带一个后缀，后缀是 U 和 L 的组合，U 表示无符号整数（unsigned），L 表示长整数（long）
```

浮点

```
带符号的指数是用 e 或 E 引入的

3.14159       /* 合法的 */
314159E-5L    /* 合法的 */
510E          /* 非法的：不完整的指数 */
210f          /* 非法的：没有小数或指数 */
.e55          /* 非法的：缺少整数或分数 */
```

字符

```
单引号，'0' '1','A'
注意转义字符; '\t' '\n'
带字符值的 \u02C0
```



字符串

```
双引号: "anc" "ssss\n"
```

枚举

```
enum Color{RED,BLUE},  RED 是字母量
```

### 变量

```
修饰词 类型 变量名; auto unsinged int uTa; 
变量初始化;  int a=2,j=0;
变量多声明用 逗号 分割;
A : 一片内存的别名
```

#### 普通变量

```
auto 可以省略
```

#### 常量

```
const 值不能改变 
字符之类的，静态区
定义常量
在 C 中，有两种简单的定义常量的方式：
使用 #define 预处理器。
使用 const 关键字。
```

#### 静态变量

```
static
局部，函数内部初始化声明，执行一次； 值可以改变 静态区
全局，值可以改变， 静态区
```

```
auto 内存变量，用于局部 栈中使用
register 寄存器变量，不能获取地址
extern 声明，不占用内存，
static 静态，静态区
```

### printf

| 格式字符 | 意义                                       |
| :------- | :----------------------------------------- |
| d        | 以十进制形式输出带符号整数(正数不输出符号) |
| o        | 以八进制形式输出无符号整数(不输出前缀0)    |
| x,X      | 以十六进制形式输出无符号整数(不输出前缀Ox) |
| u        | 以十进制形式输出无符号整数                 |
| f        | 以小数形式输出单、双精度实数               |
| e,E      | 以指数形式输出单、双精度实数               |
| g,G      | 以%f或%e中较短的输出宽度输出单、双精度实数 |
| c        | 输出单个字符                               |
| s        | 输出字符串                                 |
| p        | 输出指针地址                               |
| lu       | 32位无符号整数                             |
| llu      | 64位无符号整数                             |

| flags（标识） | 描述                                                         |
| :------------ | :----------------------------------------------------------- |
| -             | 在给定的字段宽度内左对齐，默认是右对齐（参见 width 子说明符）。 |
| +             | 强制在结果之前显示加号或减号（+ 或 -），即正数前面会显示 + 号。默认情况下，只有负数前面会显示一个 - 号。 |
| 空格          | 如果没有写入任何符号，则在该值前面插入一个空格。             |
| #             | 与 o、x 或 X 说明符一起使用时，非零值前面会分别显示 0、0x 或 0X。 与 e、E 和 f 一起使用时，会强制输出包含一个小数点，即使后边没有数字时也会显示小数点。默认情况下，如果后边没有数字时候，不会显示显示小数点。 与 g 或 G 一起使用时，结果与使用 e 或 E 时相同，但是尾部的零不会被移除。 |
| 0             | 在指定填充 padding 的数字左边放置零（0），而不是空格（参见 width 子说明符）。 |

| width（宽度） | 描述                                                         |
| :------------ | :----------------------------------------------------------- |
| (number)      | 要输出的字符的最小数目。如果输出的值短于该数，结果会用空格填充。如果输出的值长于该数，结果不会被截断。 |
| *             | 宽度在 format 字符串中未指定，但是会作为附加整数值参数放置于要被格式化的参数之前。 |

| .precision（精度） | 描述                                                         |
| :----------------- | :----------------------------------------------------------- |
| .number            | 对于整数说明符（d、i、o、u、x、X）：precision 指定了要写入的数字的最小位数。如果写入的值短于该数，结果会用前导零来填充。如果写入的值长于该数，结果不会被截断。精度为 0 意味着不写入任何字符。 对于 e、E 和 f 说明符：要在小数点后输出的小数位数。 对于 g 和 G 说明符：要输出的最大有效位数。 对于 s: 要输出的最大字符数。默认情况下，所有字符都会被输出，直到遇到末尾的空字符。 对于 c 类型：没有任何影响。 当未指定任何精度时，默认为 1。如果指定时不带有一个显式值，则假定为 0。 |
| .*                 | 精度在 format 字符串中未指定，但是会作为附加整数值参数放置于要被格式化的参数之前。 |

| length（长度） | 描述                                                         |
| :------------- | :----------------------------------------------------------- |
| h              | 参数被解释为短整型或无符号短整型（仅适用于整数说明符：i、d、o、u、x 和 X）。 |
| l              | 参数被解释为长整型或无符号长整型，适用于整数说明符（i、d、o、u、x 和 X）及说明符 c（表示一个宽字符）和 s（表示宽字符字符串）。 |
| L              | 参数被解释为长双精度型（仅适用于浮点数说明符：e、E、f、g 和 G）。 |

- **附加参数** -- 根据不同的 format 字符串，函数可能需要一系列的附加参数，每个参数包含了一个要被插入的值，替换了 format 参数中指定的每个 % 标签。参数的个数应与 % 标签的个数相同。

### 运算符号

```
算数: + - * / % 
	 ++ --   ;前置，先+1再取值，后置先取值再+1
赋值: = += -= *= /+ %=
关系: == != > >= <= <
逻辑: && || !
位操作: & | ~(取反) ^（异或） >> <<
```

### 特殊符号

```
sizeof() 操作符 取 类型或者变量的占用内存大小（字节数)
指针: &a *p ===> 取地址/获取值的指针 取值/获取指针上的值，或声明
boolean ? A :B  三元表达式 
，  参数分割，表达式分割; 从左到右
； 语句结束
()  优先级最高；
[] 数组；
```

### 类型强转

```
类型强制转换；
int a=1024001;
char b=(int)a;
```

### 类型别名

```
typedef 起别名;
type unsinged int uint;
type singed int sint;
```



## 语言结构

### 判断

```
if (<condition>){}
[else if(<condition>){}]
[else{}]

switch(a)
{
  case A: ... break;
  case B: ... break;
  default: ... break;
}
```

### 循环

```
for(i=0;i<10;i++){}
do{}while(<condition>);
while(<condition>){}

break;
continue;
goto;
标签: A:
```

### 标签

```
标签: A:
```



### goto

```
A:
  ...
goto A；
```


## 复合类型

### 指针

```
& 取变量地址； 只能右
* 变量值；
int a=10;
int *p= &a;
*p=20;

指针的本质是变量的地址；
** 二级指针，指针的指针;
```

指针的泛化；

### 1维数组

```
int *p; // 
int a[20]={0}；
int *b=(int*)malloc(80)；
p=a;
p=b;
本质: 类型相同的一片内存
数组初始化:
int arr[5]={1,2,3,4,5,6} ;// X
int arr[]={1,2,3,4,5} ;   // 自动计算长度
int arr[5]={1,2,3} ;	// 没初始化的原始默认初始化0；
int len = sizeof(arr); // sizeof(*arr);
```

### 字符串

```
本质是char类型1维数组 以 0结尾;
char a[20]; 最大长度，19个字符
char b[]="hello"  ; 长度 6；
char* str=(char*)malloc(20) ;

头文件
#include <string.h>
```

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main()
{
    int len,cmp;
    char a[20]="world";
    char b[]="hello";
    char* c=(char*) malloc(20);
    char* p=c;
    printf("a=%s,b=%s\n",a,b);

    // 拼接
    p=strcat(a,b);
    printf("a=%s,b=%s,p=%s\n",a,b,p);
    // 长度
    len=strlen(p);
    printf("strlen(p)=%d\n",len);
    // 复制
    strcpy(c,a);
    printf("a=%s,c=%s\n",a,c);
    //清空
    memset(p,0,20);
    strnset(p,0,20);
    printf("a=%s,c=%s\n",a,c);
    // 复制
    strncpy(a,c,len);
    printf("p=%s,c=%s\n",p,c);
    // 比较
    a[0] -=32;
    cmp=strcmp(a,c);
    printf("a=%s,c=%s,%d\n",a,c,cmp);
    cmp=strcasecmp(a,c);
    printf("a=%s,c=%s,%d\n",a,c,cmp);

    return 0;
}
```

### 多维数组

```
int a[4][3];
int a[10][20];
int a[2][3][4];
本质: 类型相同的一片内存
int *b=(int *)a;
```

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void printArr(int* nums,int numSize){
    register int i=0;
    printf("[");
    if(i<numSize){
         printf("%d",nums[i]);
    }
   
    for(i=1;i<numSize;i++){
        printf(",%d",nums[i]);
    }
    printf("]");
}
void printTArr(int** nums,int rowSize,int* colSize){
    register int i=0,j=0;
    printf("[");
    if(i<rowSize){
        printArr(nums[i],colSize[i]);
    }
    for(i=1;i<rowSize;i++){
        printf(",\n");
        printArr(nums[i],colSize[i]);
    }
    printf("]");
}
int main()
{
    int i,j;
    int a[3][2];
    for(i=0;i<3;i++){
        for(j=0;j<2;j++){
            a[i][j]=2*i+j;
            printf("a[%d][%d]=%d\n",i,j,a[i][j]);
        }
    }
   
    int* b=(int*)a;
    printArr(b,6);
    printf("\n");
    // 不相同的; 不能直接等
    int** c;  // 二级指针数组指针;
    int (*d)[2]=a;
    // 指针占用大小
    printf("sizeof(a)=%d,sizeof(c)=%d,sizeof(d)=%d\n",sizeof(a),sizeof(c),sizeof(d));
    for(i=0;i<3;i++){
        for(j=0;j<2;j++){
            printf("d[%d][%d]=%d\n",i,j,d[i][j]);
        }
    }

    c=(int**)malloc(3*sizeof(int*));
    for(i=0;i<3;i++){
        c[i]=a[i];
    }
    for(i=0;i<3;i++){
        for(j=0;j<2;j++){
            printf("c[%d][%d]=%d\n",i,j,c[i][j]);
        }
    }
    // 指针数组
    int* e[3];
    for(i=0;i<3;i++){
        e[i]=a[i];
    }
    for(i=0;i<3;i++){
        for(j=0;j<2;j++){
            printf("e[%d][%d]=%d\n",i,j,c[i][j]);
        }
    }
    int colSize[3]={2,2,2};
    printTArr(e,3,colSize);
    printf("\n");
    return 0;
}
```



### 数组指针

```c
int (*d)[2]=a;  // 数组指针, 本质是指针，占4字节;  一个地址的长度;
int* e[3];      // 指针数组， 本质是数组
int**           // 二级指针,
```



### 结构体

```
struct STRUCTNAME{
   type name;
   ....
};

struct Student{
	int id;
	char* name;
};

```

### 联合体

```
struct Point{
	int x,y;
}
union Rect{
	struct {
	 struct Point a;
	 struct Point b;	
	} points;
	int arr[4];
}；
// 最大对齐
sizeof(union Rect)
```



### 枚举

```
enum GREAD{
    A,B,C
};
enum CLASS{
    ONE=1,TWO,FHREE
};
// 枚举声明完后，里面的都对整数值; 整数的扩展
```

### 位域

占用位数; 会分割;

```
struct AA{
	int a:3;
	int b:5;
};
```


### const

1. const 伪常量

```
	const int a = 20;
//	a = 30;  // a为常量不能再赋值，编译不通过
	int *p = &a;
	printf("a=%d\n", a);
	*p = 30;              // 通过变量指针p 指向a的地址； 通过*p 修改值;
	printf("a=%d\n", a);
```

```
a=20
a=30
```

2. const指针

```
3种样式:
const int *p = &a;   // *p 是const
int const *p = &a;   // *p 是const  const 放int 前后效果一样
int *const p = &a;   //  p 是const  int* 是const; 
复合样式:
const int* const p = &a;   //  p和*p 是const 
核心点: const 后面的不能修改;
```

### 指针++

```c
	int arr[] = {1, 9, 14};
	int len = sizeof(arr) / sizeof(*arr);
	int *p = arr;
	int i;
	for (i = 0; i < len;i++){
		printf("[%p]=%d\n", &arr[i], arr[i]);
	}
	printf("[%p]=%d\n", p, *p);
	*++p;
	printf("[%p]=%d\n", p, *p);
	++*p;
	printf("[%p]=%d\n", p, *p);
	*p++;
	printf("[%p]=%d\n", p, *p);
	(*p)++;
	printf("[%p]=%d\n", p, *p);
```

```
[0061FEB8]=1
[0061FEBC]=9
[0061FEC0]=14
[0061FEB8]=1
[0061FEBC]=9
[0061FEBC]=10
[0061FEC0]=14
[0061FEC0]=15
```

++ 后是谁谁++； 无括号 ++ 优先*---- 说法本身错误；

## 函数



### 函数

```
void fun()
void hello(int a)

返回值 函数名(参数列表)
（void）
函数类型: typedef int (*PFun)(int);  ----> PFun p; p为指针类型
typedef int Fun(int); -----> Fun *p; p为函数指针   
```

### inline

**内联函数**

提高函数的执行效率 **一处内联函数的调用都要复制代码，将使程序的总代码量增大，消耗更多的内存空间**

```
2、inline的使用是有所限制的

      inline只适合涵数体内代码简单的函数数使用，不能包含复杂的结构控制语句例如while、switch，并且内联函数本身不能是直接递归函数(自己内部还调用自己的函数)。
```

### 函数指针

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#define EMPTY ""

typedef int (*Calc)(int,int);
struct function_meta {
    Calc func_ptr;
    char * func_name;
} ; 

int add(int a,int b){
    return a+b;
}
int sub(int a,int b){
    return a-b;
}
int max(int a,int b){
    return a-b>0 ? a: b;
}
int min(int a,int b){
    return a-b<0 ? a: b;
}
 // 函数元数据数组
struct function_meta arrfunc_ptrs[4] = {
                                            {add, "add"}, 
                                            {sub, "sub"}, 
                                            {max, "max"},
                                            {min, "min"}
                                        }; 
// 查找函数名
char* find_func_name(Calc calc){
    int i;
    char *name=EMPTY;
    // 函数名
    for(i=0;i<4;i++){
        if(calc == arrfunc_ptrs[i].func_ptr ){
            name=arrfunc_ptrs[i].func_name;
            break;
        }
    }
    return name;
}
void pp(Calc calc,int a,int b){
    // 找函数名
	char *name=find_func_name(calc);
    // 回调函数 calc(a,b)
    printf("%s(%d,%d)=%d\n",name,a,b,calc(a,b));
}
int main(){
    int a=127,b=39;
    pp(add,a,b);
    pp(sub,a,b);
    pp(max,a,b);
    pp(min,a,b);
    return 0;
}
```
### 函数参数

```
类型 ； // 可以理解为局部变量，会复制调用处传参，为函数参数赋值；
// 形参实参 -- 不容易理解;  赋值类型: 值，指针
```



### 数组参数

数组做函数参数:

```
void printArr(int* nums,int numSize);
void printTArr(int** nums,int rowSize,int* colSize);
```

### 递归

```
函数内部调用自己;
一定有返回条件; --> 二叉树
```

```c

```

### 可变参数

```
#include <stdarg.h>
int func(int, ... ) 
核心: 第一个参数可以知道参数的长度;
```

```c
#include <stdio.h>
#include <stdarg.h>
 
double average(int num,...)
{
 
    va_list valist;
    double sum = 0.0;
    int i;
 
    /* 为 num 个参数初始化 valist */
    va_start(valist, num);
 
    /* 访问所有赋给 valist 的参数 */
    for (i = 0; i < num; i++)
    {
       sum += va_arg(valist, int);
    }
    /* 清理为 valist 保留的内存 */
    va_end(valist);
 
    return sum/num;
}
 
int main()
{
   printf("Average of 2, 3, 4, 5 = %f\n", average(4, 2,3,4,5));
   printf("Average of 5, 10, 15 = %f\n", average(3, 5,10,15));
}
```



## 常用函数

### IO

```
字符串 gets puts
字符 getchar putchar
scanf/printf
```

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main(int argc, char const *argv[])
{
    int id=10;
    char name[16];
    char c;
    int i=0;
    char *p;
    // 1. scanf/printf
    scanf("%d", &id);
    scanf("%s", name);
    printf("a=%d,name=%s\n",id,name);

    fflush(stdin);
    // 2. 字符 getchar putchar
    while((c=getchar()) != '\n'){
        name[i++]=c;
    }
    name[i]=0;
    fflush(stdout);
    i=0;
    c=name[i++];
    while(c != '0'){
        putchar(c);
        c=name[i++];
    }

    fflush(stdin);
     fflush(stdout);
    // 3.字符串 gets puts
    p=gets(name);
    puts(p);
    
    return 0;
}
```



### 文件读写

```
fopen/fclose
fprintf/fscanf  fgets/fputs  fgetc/fputc  fread/fwrite
fseek(FILE *_File,long _Offset,int _Origin)
SEEK_SET	文件的开头
SEEK_CUR	文件指针的当前位置
SEEK_END	文件的末尾
long ftell(FILE *_File);
fgetpos(fp, &position); fsetpos(fp, &position); 
```

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void w(const char* fn){
   FILE *fp = NULL;
 
   fp = fopen(fn, "w+");
   fprintf(fp, "This is testing for fprintf...\n");
   fputs("This is testing for fputs...\n", fp);
   fclose(fp);
}
void r(const char* fn){
   FILE *fp = NULL;
    char buff[255];
   fp = fopen(fn, "r+");

   fscanf(fp, "%s", buff);
   printf("1: %s\n", buff );
 
   fgets(buff, 255, (FILE*)fp);
   printf("2: %s\n", buff );
   
   fgets(buff, 255, (FILE*)fp);
   printf("3: %s\n", buff );

   fclose(fp);
}
int main(int argc, char const *argv[])
{
    char* fn="D:\\linux\\c\\ct\\base\\tmp.txt";
    w(fn);
    r(fn);
    return 0;
}
```

### 内存管理

内存管理函数

```
void *calloc(int num, int size);
void free(void *address);
void *malloc(int num);
void *realloc(void *address, int newsize);
```

内存对齐模式

大端对齐 : 内存中数据是高位到低位分布; 返回的是高位所在存储的指针

小端对齐 : 内存中数据是低位到高位分布;返回的是低位所在存储的指针

```c
union check{
	uint32_t i;
	char ch;
} checkUseCase;

// 1/大段 0/小端
int checkSystemStorageMode()
{
	checkUseCase.i = 0x1;
	return ((int)(checkUseCase.ch));
}
// 判断大小端
int check_sys()
{
  int i=1;
  return (*(char *)&i);
}
```

内存分段

```
代码段：只读权限，指令，常量 静态变量 字面量
数据段 已初始化的静态变量和全局变量
BBS段 未被初始化的静态变量和全局变量
栈 存储的是局部变量，系统控制
堆 :手动申请的内存 malloc申请的内存
```

### 时间函数

```c
	time_t rawtime;
	struct tm *timeinfo;
	char buffer[128];
	const char *former = "%Y-%m-%d %H:%M:%S";
	time (&rawtime);
	printf("%ld\n", rawtime);

	timeinfo = localtime (&rawtime);
	strftime (buffer,sizeof(buffer),former,timeinfo);
	printf("Now is %s\n", buffer);
```

### 头文件

```
#include <ff>  // 系统文件 c++的，省.h
#include <ff.h> // 系统文件 
#include "ff.h" // 自定义的文件
```

### 预处理

| 指令     | 描述                                                        |
| :------- | :---------------------------------------------------------- |
| #define  | 定义宏                                                      |
| #include | 包含一个源代码文件                                          |
| #undef   | 取消已定义的宏                                              |
| #ifndef  | 如果宏没有定义，则返回真                                    |
| #if      | 如果给定条件为真，则编译下面代码                            |
| #else    | #if 的替代方案                                              |
| #elif    | 如果前面的 #if 给定条件不为真，当前条件为真，则编译下面代码 |
| #endif   | 结束一个 #if……#else 条件编译块                              |
| #error   | 当遇到标准错误时，输出错误消息                              |
| #ifdef   | 如果宏已经定义，则返回真                                    |
| #pragma  | 使用标准化方法，向编译器发布特殊的命令到编                  |

### 宏

预定义宏

| 宏        | 描述                                                |
| :-------- | :-------------------------------------------------- |
| \__DATE__ | 当前日期，一个以 "MMM DD YYYY" 格式表示的字符常量。 |
| \__TIME__  | 当前时间，一个以 "HH:MM:SS" 格式表示的字符常量。    |
| \__FILE__  | 这会包含当前文件名，一个字符串常量。                |
| \__LINE__  | 这会包含当前行号，一个十进制常量。                  |
| \__STDC__  | 当编译器以 ANSI 标准编译时，则定义为 1。            |
| \__FUNC__  | 当前函数的名字 |

重要的符号

| 符号 | 说明         | 举例                                                         |
| ---- | ------------ | ------------------------------------------------------------ |
| \\   | 宏延续运算符 | #define  message_for(a, b)  \ 	printf(#a " and " #b ": We love you!\n") |
| \#   | 字符串常量化 | #define  message_for(a, b) 	printf(#a " and " #b ": We love you!\n") |
| \##  | 宏延续运算符 | #define tokenpaster(n) printf ("token" #n " = %d", token##n) |
参数化宏

```
#define MAX(x,y) ((x) > (y) ? (x) : (y))
// 宏和内联的区别，1. 类型校验;
```



### 错误处理



```
errno、perror() 和 strerror()

extern int errno ;  使用错误号
perror 打印错误；
char *strerror(int)  由错误号查找错误信息

```

### 断言

测试一个条件并可能使程序终止

```
#include <assert.h>
void assert( int expression );
断言： 表达式为假 ，返回错误号并结束
使用assert的缺点是，频繁的调用会极大的影响程序的性能，增加额外的开销
```

### 动态库

```c
.h 声明
#ifndef _LIBNAME_H
#define _LIBNAME_H

#ifdef __cplusplus
#if __cplusplus
extern "C"{
#endif
#endif /* __cplusplus */

extern void FUN(...);

#ifdef __cplusplus
#if __cplusplus
}
#endif
#endif /* __cplusplus */
#endif // _LIBNAME_H

.c 定义
void FUN(...){}

```

编译

```
# 编译动态库
gcc -fPIC -shared hello.c -o libhello.so
gcc test.c -lhello -L. -o test
```

### 静态库

编译

```
1. gcc -c hello.c 注意这里没有使用-shared选项
2. 把目标文件归档    ar -r libhello.a hello.o
ar -crv libmyhello.a hello.o
    程序 ar 配合参数 -r 创建一个新库 libhello.a 并将命令行中列出的对象文件插入。采用这种方法，如果库不存在的话，参数 -r 将创建一个新的库，而如果库存在的话，将用新的模块替换原来的模块。
3. 在程序中链接静态库
          gcc -o test test.c -L. -lhello  
或者   gcc test.c libhello.a -L. -o hello.static

生成的hello.static就不再依赖libhello.a了

编译静态库
```

## 常用库
| .    | 库   | 说明 |
| ---- | ---- | ---- |
| 1 |<errno.h>   | 错误码 |
| 2 |<float.h>   | 浮点数 |
| 3 |<limits.h>  |  |
| 4 |<locale.h>  | |
| 5 |<math.h>    | 数学 |
| 6 |<signal.h>  | 信号量 |
| 7 |<setjmp.h>  | 跳转 |
| 8 |<stdarg.h>  | 可变参数 |
| 9 |<stddef.h>  | 宏定义 |
| 10|<stdio.h>   | io |
| 11|<string.h>  | 字符串 |
| 12|<stdlib.h>  | 标准类库 |
| 13|<time.h>    | 时间 |








