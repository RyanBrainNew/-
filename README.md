准备创建动态链接库的 源材料: .c 、 .h 文件，这里用tomato.h 和tomato.c文件  
编写Makefile:  
（1）在第二行-fPIC 作用:让编译器将我们的源文件tomato.c编译成位置无关码。  
（2）在第三行，我们直接使用gcc 来编译，不用像创建静态链接库时用ar 工具。  
（3）在第三行最后，添加 -shared ， 让编译器生成动态链接文件。  
此时make即可，ls可以看到已经生成libfruit.so文件  
创建测试文件test.c ，并将生成的libfruit.so和头文件tomato.h加入到test.c路径下  
把动态库复制到/usr/lib64下，gcc -o test test.c -lfruit -L.  即可运行test  
