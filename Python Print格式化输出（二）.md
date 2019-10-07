# 通过format方法对Print格式化输出  
相对基本格式化输出采用‘%’的方法，format()功能更强大，该函数把字符串当成一个模板，通过传入的参数进行格式化，并且使用大括号‘{}’作为特殊字符代替‘%’  

## 基本用法：  
+ 直接按顺序传入参数：{}，不加内容  
+ 按参数位置传入参数：{2}，加入顺序编号；引申，可通过list方式多参数批量输入  
+ 按参数名称传入参数：{name}，加入参数名;引申，可通过键值对方式多参数批量输入  

*示例*  
```Python
print("{} {}".format("hello", "world")            # 不设置指定位置，按默认顺序
print("{1} {2}".format("hello", "world")          # 设置指定位置，按指定顺序输入
print("{a} {b}".format(a="hello", b="world")      # 设置指定参数名，按参数名输入

#通过list输入
my_list = ["hello","world"]
print("{0[0]} {0[1]}".format(my_list))

#通过键值对输入
my_dic = {"a":"hello","b":"world"}
print("{a} {b}".format(**my_dic))

```

## 进阶用法：  
格式说明：  

| : |<填充>|<对齐>|<宽度>| , |<精度>|<类型>|
|:----:|:-----------:|:--------:|:----------:|:-----------:|:-----------------:|:---------------:|
|引导符|用于填充，<br>默认西文空格|< 左对齐 <br> > 右对齐 <br> ^ 中对齐|槽宽度|数字千位分割符|浮点数的小数部分精度或<br>字符串最大输出长度|整数类型b,c,d,o,x,X <br>浮点类型e,E,f,%|

```
Format Specification
format_spec     ::=  [[fill]align][sign][#][0][width][grouping_option][.precision][type]
fill            ::=  <any character>
align           ::=  "<" | ">" | "=" | "^"
sign            ::=  "+" | "-" | " "
width           ::=  digit+
grouping_option ::=  "_" | ","
precision       ::=  digit+
type            ::=  "b" | "c" | "d" | "e" | "E" | "f" | "F" | "g" | "G" | "n" | "o" | "s" | "x" | "X" | "%"  
```

*示例*  
```Python
#对齐格式演示
mylist = ['orange', 'apple', 'zoo', 'internationalization', 'blueberry']
tp = "{:<8}\t{:>8}\t{:<8}\t{:^30}\t{:>10}"
print(tp.format(*"12345"))
print(tp.format(*mylist))

#填充字符
print("{:*^30}".format("GOOD"))

#编码类型
for num in range(5,12):
    for base in 'dXob':
        print('{0:{width}{base}}'.format(num, base=base, width=5), end=' ')
    print()

```
