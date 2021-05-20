# helloFFMPEG  
ffmpeg demo by Android studio 4.2  
基于2021-05-20号Android studio最新环境下编译的ffmpeg工程。  
移植过程中大致需要做注意以下步骤  
1.将so和头文件拷贝至`ffmpeg\app\src\main\ffmpeg`  
2.ffmpeg\app\build.gradle添加添加cpu支持`abiFilters 'armeabi-v7a','arm64-v8a','x86','x86_64'`  
3.ffmpeg\app\src\main\cpp\CMakeLists.txt注意头文件路径和so路径定义`8行`和第`10行`。  
4.ffmpeg\app\src\main\cpp\CMakeLists.txt注意CPU指令集的定义需要列如`${ANDROID_ABI}`，需要构建编译时so与之对应的路径。  
5.ffmpeg\app\src\main\cpp\native-lib.cpp引入头文件的定义，由于使用了C++语言方式调用ffmpeg，引入头文件时需要放置在`extern "C"{xxx}`中  
