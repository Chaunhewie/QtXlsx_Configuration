# QtXlsx_Configuration
本页记载自己安装QtXlsx的过程

配置：x64 windows10 VS2017 Qt5.9.2

1.	首先根据网上的资料查询并下载perl：
	网址https://www.activestate.com/activeperl/downloads
	选择	ACTIVEPERL
	    5.24.3.2404
	    Windows Installer (EXE)
	默认安装，完成后cmd输入perl -v，得到This is perl 5, version 24, subversion 3 (v5.24.3)...

2.	下载QtXlsx源码包：
	https://github.com/VSRonin/QtXlsxWriter 打包下载即可

3.	解压到C盘C:\QtXlsxWriter-master

4.	开始菜单，搜索并打开Qt 5.9.2 64-bit for Desktop (MSVC 2017)

5.	搜索并打开vcvarsall.bat路径，我的是 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Auxiliary\Build 路径下

6.	在Qt 5.9.2 64-bit for Desktop (MSVC 2017) 命令框中依次输入如下命令并执行：

	cd /d C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\VC\Auxiliary\Build

	vcvarsall.bat amd64
	
	cd /d C:\QtXlsxWriter-master\src
	
	qmake src.pro
	
	nmake
	
	nmake install
	
7.	完成配置

遇到的问题：
	开始并未选择在C盘，而是放在自己的Qt路径下：E:\Scripts()Qt\QtXlsxWriter-master
	结果报如下错误：
		此处不应存在Qt\QtXlsxWriter-master\src\xlsx\xlsx.pro，原因是自己的路径中存在括号 )，使得命令分析出错
