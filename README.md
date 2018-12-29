# one-key-kms
在Linux上一键搭建KMS服务器

特别感谢KMS服务器程序的开发者Wind4


KMS服务器软件vlmcsd Github主页：https://github.com/Wind4/vlmcsd

`现在还处于测试阶段，您的服务器出现任何问题本人与服务器程序作者均不承担任何责任。`

请根据自己的服务器操作系统运行对应的脚本。

CentOS，Redhat，Fedora等请选择CentOS脚本

Debian，Ubuntu，Mint等请选择Debian脚本

##kms.sh管理脚本的使用：

如果您使用这里的一键脚本安装，即可完美使用该脚本，否则需要手动更改可执行文件存放路径

只有start/stop/restart/status的功能，直接执行即可

./kms.sh start

这样。
使用命令：

#CentOS，Redhat，Fedora等请选择CentOS脚本
wget https://raw.githubusercontent.com/dakkidaze/one-key-kms/master/one-key-kms-centos.sh
chmod +x one-key-kms-centos.sh
./one-key-kms-centos.sh

#Debian，Ubuntu，Mint等请选择Debian脚本
wget https://raw.githubusercontent.com/dakkidaze/one-key-kms/master/one-key-kms-debian.sh
chmod +x one-key-kms-debian.sh
./one-key-kms-debian.sh

#启动KMS
wget https://raw.githubusercontent.com/dakkidaze/one-key-kms/master/kms.sh
chmod +x kms.sh
./kms.sh start
注意放行服务器1688端口！

激活Windows
系统需要是VL版本的，然后使用管理员权限运行cmd，运行以下命令：

cd /d "%SystemRoot%\system32"
slmgr /skms ip  #ip为你KMS的IP地址或者域名 
slmgr /ato
slmgr /xpr
看到网上还有很多系统不是VL版本的激活方法，这个方法就不说了，感觉没啥用，因为不是VL版本的都没KEY，比如说旗舰版，家庭高级版等。

激活Office
首先你的Office必须是VOL版本，否则无法激活。

找到你的Office安装目录，如果你不知道你的Office装在哪个目录，可以鼠标右键一个程序图标比如Word，然后选择“打开文件所在的位置”，在上面地址栏就可以看到了。

这里以Office2016为例，32位文件夹目录为C:\Program Files (x86)\Microsoft Office\Office16。62位目录为C:\Program Files\Microsoft Office\Office16。关于文件夹对应的版本说明：Office16是Office2016，Office15就是Office2013，Office14就是Office2010。

下面以32位为参考。使用管理员权限运行cmd，运行以下命令：

#进入Office文件夹执行命令
cd "C:\Program Files (x86)\Microsoft Office\Office16"
cscript ospp.vbs /sethst:ip  #ip为你KMS的IP地址或者域名
cscript ospp.vbs /act
如果提示看到successful的字样，那么就是激活成功了，重新打开Office就好。
