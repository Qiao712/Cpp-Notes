## stdlib.h
* malloc(size)
* free(ptr)
* memcpy(from, to, size)
* atoi(string)  字符串转int
* atof(string)  float
* atol(string)  long
## string.h
* strcmp(a,b)
* strcpy(to, from)
* strcat(a,b)  拼接
## stdio.h
* int sprintf(char *string, char *format [,argument,...]) 字符串格式化

## ctype.h 头文件中对字符的判断函数
```
isalnum()  如果参数是字母数字，即字母或者数字，函数返回true
isalpha()  如果参数是字母，函数返回true
iscntrl()  如果参数是控制字符，函数返回true
isdigit()  如果参数是数字（0－9），函数返回true
isgraph()  如果参数是除空格之外的打印字符，函数返回true
islower()  如果参数是小写字母，函数返回true
isprint()  如果参数是打印字符（包括空格），函数返回true
ispunct()  如果参数是标点符号，函数返回true
isspace()  如果参数是标准空白字符，如空格、换行符、水平或垂直制表符，函数返回true
isupper()  如果参数是大写字母，函数返回true
isxdigit() 如果参数是十六进制数字，即0－9、a－f、A－F，函数返回true
tolower()  如果参数是大写字符，返回其小写，否则返回该参数
toupper()  如果参数是小写字符，返回其大写，否则返回该参数
``` 