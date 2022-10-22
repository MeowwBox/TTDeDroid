# TTDeDroid
[![Build Status](https://github.com/tp7309/TTDeDroid/actions/workflows/build.yaml/badge.svg?branch=master)](https://github.com/tp7309/TTDeDroid/actions/workflows/build.yaml)
[![DeepSource](https://deepsource.io/gh/tp7309/TTDeDroid.svg/?label=active+issues&show_trend=true)](https://deepsource.io/gh/tp7309/TTDeDroid/?ref=repository-badge)
<!-- [![codecov](https://codecov.io/gh/tp7309/TTDeDroid/branch/master/graph/badge.svg?token=lyEWTqfeb9)](https://codecov.io/gh/tp7309/TTDeDroid) -->

一键反编译 **apk/aar/dex/jar**，没什么技术含量，只是调调工具命令，处理些兼容性问题，会视反编译库的更新情况更新工具版本。

> - update at 2022-10-22
>
> - jadx=1.4.5
> - Storyyeller/enjarify(build by source)
> - dex2jar(build by source)
> - fernflower=222.4345.14(IntelliJ IDEA official decompiler)
> - apktool=2.6.1

# 使用要求
只是使用的话**不需要**手动安装python环境。

## 快速开始

### Windows
1. [去release页下载](https://github.com/tp7309/TTDeDroid/releases)，有中国下载地址能下载快些，也可以直接下载源码。
2. 将`TTDedroid\bin`目录的 **绝对路径** 加入`PATH`环境变量。

之后便可以在任何目录执行下面的目录反编译`*.apk/*.aar/*.dex/*.jar`文件，反编译完成后图形界面会自动打开。
```
showjar test.apk
```

### Mac/Linux
[去release页下载](https://github.com/tp7309/TTDeDroid/releases)，有中国下载地址能下载快些。
```bash
//也可以直接下载源码，中国下载慢，不推荐。
//git clone --depth=1 https://github.com/tp7309/TTDeDroid.git ~/Documents/TTDeDroid

//给脚本执行权限
chmod a+x ~/Documents/TTDeDroid/bin/showjar

//添加脚本执行路径到环境变量
showjardir='export PATH=$PATH:'$HOME/Documents/TTDeDroid/bin
# Mac
echo $showjardir >> ~/.bash_profile && source ~/.bash_profile
# Linux
echo $showjardir >> ~/.bashrc && source ~/.bashrc
```

之后便可以在任何目录执行下面的命令反编译`*.apk/*.aar/*.dex/*.jar`文件，反编译完成后图形界面会自动打开。
```bash
showjar test.apk
```

## 使用

```
usage: showjar.py [-h] [-o [OUTPUT]] [-r [RES]] [-e [ENGINE]] file

Android一键反编译工具

必选参数:
  file                  输入文件路径, *.apk/*.aar/*.dex/*.jar

可选参数:
  -h, --help            显示帮助信息
  -o [OUTPUT], --output [OUTPUT]
                        反编译文件输出目录，可选 (默认: None)
  -r [RES], --res [RES]
                        指定是否要反编译资源文件, 0:禁用, 1:启用 (默认: 0)
  -e [ENGINE], --engine [ENGINE]
                        反编译引擎, [jadx, dex2jar, fernflower, enjarify] (默认:
                        jadx)
```
