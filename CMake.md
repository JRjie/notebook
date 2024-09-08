# 关键字

---

```cmake
add_executable(main add.cpp main.cpp) #使用指定的源文件来生成目标可执行文件
```

```cmake
add_compile_options(-g -Wunused) #给后续的目标加上编译选项
```

```cmake
target_compile_options(main PUBLIC -Wall -Werror) #给指定目标加上编译选项
```

```cmake
file(GLOB_RECURSE XXX "src/*.cpp") #获取src目录下所有cpp文件，并将其保存到变量中
```

```cmake
include_directories(./) #添加头文件搜索路径
```

```cmake
set(XXX ./mul/mul.cpp) #设置源文件变量
```

```cmake
add_library(xxx STATIC ${XXX}) #指定从某些源文件创建静态库文件
```

```cmake
target_link_directories(main PUBLIC ./) #给目标添加静态库搜寻路径
```

```cmake
target_link_libraries(main xxx) #给目标链接静态库
```

```cmake
link_directories(./) #给所有目标添加静态库搜寻路径
```

```cmake
link_libraries(xxx) #给所有目标链接静态库
```

```cmake
add_library(xxx SHARED ${XXX}) #指定从某些源文件创建动态库文件
```

---

# 命令

```powershell
cmake .
```

生成Makefile

```powershell
make
```

根据Makefile执行编译

# 模板

```cmake
cmake_minimum_required(VERSION 3.14) #设定最低版本(必须)

project(hello) #指定工程名称（必须）

set(CMAKE_CXX_STANDARD 11) #设置C++标准

include_directories(./ ./include) #添加多个头文件搜索路径

file(GLOB_RECURSE XXX "src1/*.cpp" "src2/*.cpp") #获取多个目录下所有cpp文件，并将其保存到变量中

set(XXX ./mul/mul.cpp) #设置源文件变量

add_library(xxx STATIC ${XXX}) #指定从某些源文件创建库文件
                               #xxx:库名称
                               #STATIC:静态库
                               #XXX:源文件

target_link_directories(main PUBLIC ./) #给目标添加静态库搜寻路径
                                        #适用于所有链接到这个目标的其他目标

target_link_libraries(main xxx) #给目标链接静态库

add_compile_options(-g -Wunused) #给后续的目标加上编译选项
                                 #-g:可调试
							  #-Wunused:未用到的变量输出warning

add_executable(main add.cpp ${XXX} main.cpp) #生成可执行文件（必须）

target_compile_options(main PUBLIC -Wall -Werror) #给指定目标加上编译选项
                                                  #PUBLIC:编译选项不仅适用于目标本身，还会传递给依赖于该目标的其他目标
                                                  #-Wall:启用所有常见的警告
                                                  #-Werror:将警告视为错误
```

 

