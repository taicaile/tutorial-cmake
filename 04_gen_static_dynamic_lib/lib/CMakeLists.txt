SET(LIBHELLO_SRC hello.cpp)

# generate shared lib
# ADD_LIBRARY(hello SHARED ${LIBHELLO_SRC})

# generate static lib
# ADD_LIBRARY(hello STATIC ${LIBHELLO_SRC})

# 同时构建静态库和动态库

ADD_LIBRARY(hello_static STATIC ${LIBHELLO_SRC})
# 对 hello_static 重命名为 hello
SET_TARGET_PROPERTIES(hello_static PROPERTIES OUTPUT_NAME "hello")
# cmake 在构建一个新的 target 时，会尝试清理掉其他使用这个名字的库
SET_TARGET_PROPERTIES(hello_static PROPERTIES CLEAR_DIRECT_OUTPUT 1)


ADD_LIBRARY(hello SHARED ${LIBHELLO_SRC})
SET_TARGET_PROPERTIES(hello PROPERTIES OUTPUT_NAME "hello")
SET_TARGET_PROPERTIES(hello PROPERTIES CLEAR_DIRECT_OUTPUT 1)
