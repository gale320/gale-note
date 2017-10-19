qt cmake 
=======================
使用cmake构建Qt应用
1、moc的使用
   在CMakeLists.txt加入
    set(CMAKE_AUTOMOC ON)
   继承了QObject的类，需要在实现部分包含moc_xxx.cpp，cmake编译时会自动寻找xxx.h的文件，生成moc_xxx.cpp的文件

2、ui文件的使用
     在CMakeLists.txt加入
    set(CMAKE_AUTOUIC ON)  
    在使用时需要包含ui_xxx.h，cmake寻找xxx.ui生成ui_xxx.h的文件

3、qrc文件的使用 
  在CMakeLists.txt加入
  	set(CMAKE_AUTORCC ON)

   使用时包含rcc_xxx.cpp文件。

