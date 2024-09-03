# 关键字

---

```cmake
add_executable(main main.cpp) #使用指定的源文件来生成目标可执行文件
```

```cmake
add_compile_options(-g -Wunused) #给后续的目标加上编译选项
```

```cmake
target_compile_options(main PUBLIC -Wall -Werror) #给指定目标加上编译选项
```

```cmake

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

add_compile_options(-g -Wunused) #给后续的目标加上编译选项
                                 #-g:可调试
							  #-Wunused:未用到的变量输出warning

add_executable(main main.cpp) #生成可执行文件（必须）

target_compile_options(main PUBLIC -Wall -Werror) #给指定目标加上编译选项
                                                  #PUBLIC:编译选项不仅适用于目标本身，还会传递给依赖于该目标的其他目标
                                                  #-Wall:启用所有常见的警告
                                                  #-Werror:将警告视为错误
```


