### 初始化

    //初始化
    string s1 = "abc";  //拷贝初始化
    string s2("abc");   //直接初始化
    string s3(10,'c');
    string s4(cp,n);    //cp指向的数组中的前n个字符
    string s5(s1,pos);   //从s1中下标pos开始拷贝
    string s6(s1,pos,len); //从s1中下标pos开始拷贝len长

### 操作
    s1[0];
    s1.empty();
    string::size_type l = s1.size();  //返回一种无符号类型
    s1 + s2;
    s1 + "123"; //转型
    s1 == s2;
    s1 > s2;    //字典顺序
    s1.find(目标字符/字符串) 
    s.append(args); //追加
    s.replace(range, args);     //替换。range是下标+长度 或 迭代器
    s.compare(...)

#### 搜索操作
都返回string::size_type表示下标，如果失败返回string::npos 
#### 数值转换
* to_string(val)
* stoi(string, pos, base)  int
* stol(string, pos, base)  long
* stoll(string, pos, base) long long
* stoul(string, pos, base) unsigned long
* stoull(string, pos, base) unsigned long long
* stof(string, pos) float
* stod(string, pos) double
* stold(string, pos) long double
* (pos:起始位置下标; base:基数 默认为10)
* (如果string不能转换为字符，抛出invalid——argument)
* (如果数值保存不下抛出out_of_range)


```
    s.find(args)    //第一次出现位置
    s.rfind(args)   //第二次出现位置
    s.find_first_of(args) //在s中查找args中任意一个字符第一次出现的位置
    s.find_last_of(args)
    s.find_first_not_of(args)
    s.find_last_not_of(args)
```

args可以是,pos/n可以没有
* char, pos
* s2, pos
* char*, pos
* char*, pos, n

#### 遍历 c++11 -- 范围for（range for）
    for(auto c : s1){
        cout<<c<<endl;
    }
    
    //若要操作序列中元素，使用引用
    for(auto &c:s1){
        
    }
    
#### cctype 头文件中对字符的判断函数
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

### c风格字符串 
    #include<cstring>
    
    strlen(p)
    strcmp(p1,p2) p1=p2返回0,p1>p2返回正数，p1<p2 负数
    strcat(p1,p2) p1 = p1 + p2, 并返回p1
    strcpy(p1,p2) p1 = p2, 并返回p1
    strstr(p1,p2) 判断p2是不是p1的子集
    strdup(p1) //复制p1，内部使用malloc，需使用free释放

##### string->char*
    const char *p = s.c_str();\
    

