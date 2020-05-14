#设置项目名称 HELLO
PROJECT (HELLO)

#变量SRC_LIST 赋值 main.cpp
SET(SRC_LIST main.cpp)

#MESSAGE 输出log 
#SEND_ERROR，产生错误，生成过程被跳过
#SATUS，输出前缀为—的信息
#FATAL_ERROR，立即终止所有 cmake 过程
#${}取出变量值
MESSAGE(STATUS "This is BINARY dir " ${HELLO_BINARY_DIR}) 


#隐式变量 HELLO_SOURCE_DIR 即  <项目名称>_SOURCE_DIR
#同时 cmake 系统也帮助我们预定义了 PROJECT_BINARY_DIR 和 PROJECT_SOURCE_DIR 变量，他们的值分别跟 HELLO_BINARY_DIR 与 HELLO_SOURCE_DIR 一致。
#最好用PROJECT_BINARY_DIR这两个，因为这样改了项目名称对文件也没有影响
MESSAGE(STATUS "This is SOURCE dir " ${HELLO_SOURCE_DIR}) 

#ADD_EXECUTABLE 生产执行文件
ADD_EXECUTABLE(hello.o ${SRC_LIST})
