# change_jdk
在Android官网中，提示编译不同版本的android SDK需要的java版本可能会不同，所以在编译时可能需要切换jdk版本，为方便管理，我们写成一个脚本，通过脚本在shell中快速切换jdk。

## 脚本使用说明
### 一.实现shell脚本切换JDK的步骤
#### 1.确定多个JDK版本的安装路径
我电脑里安装了jdk1.8 和 jdk1.6 两个版本，安装路径都在`/usr/lib/jvm`目录下:

`/usr/lib/jvm/java-8-openjdk-amd64/`

`/usr/lib/jvm/jdk1.6.0_45/`

#### 2.根据上面的jdk安装路径，修改脚本文件change_jdk
	如果电脑里的安装路径不是上面两个目录，修改脚本里的“JAVA_HOME”，匹配成你电脑的jdk安装路径

#### 3.设置通过脚本名称可以在任意目录执行脚本
我的脚本文件放在 `~/tools/change_jdk` 目录下，在系统环境管理文件 .bashrc(根目录下) 或者 /etc/profile文件添加一行代码：
```
export PATH=~/work/tools:$PATH
```

#### 4.打开终端，在任意目录执行以下命令都可以切换jdk版本
- 若切换到jdk 1.8 ,执行命令:
```
source change_jdk 1.8
```
- 若切换到jdk 1.6 ,执行命令:
```
 source change_jdk 1.6
```
