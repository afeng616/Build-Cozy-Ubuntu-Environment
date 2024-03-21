# 修复Ubuntu引导

这两天又在折腾系统，没想到把Ubuntu的引导给搞坏了，导致开机无法找到之前的Ubuntu引导，无法进入Ubuntu系统。  
在网上各种资料都没有解决我的问题，最后在csdn上找到了一个repair的方案[^method]。

## 准备工作

1. 与安装Ubuntu系统的准备工作一样，将系统镜像烧录到U盘里，这里就不赘述了；
2. 进入系统安装引导后，依然选择第一项`try or install ubuntu`；
3. 进入系统后，选择左侧的`try ubuntu`；
4. <kbd>Ctrl</kbd><kbd>Alt</kbd><kbd>T</kbd>打开终端，输入以下命令，安装`boot-repair`工具；
```shell
sudo add-apt-repository ppa:yannubuntu/boot-repair
sudo apt-get update
sudo apt-get install -y boot-repair
```
5. 运行`boot-repair`工具，选择`Recommended repair`，等待工具自动修复引导问题；
6. 弹出`Boot successfully repaired`提示后，重启电脑，即可看到引导界面，选择`Ubuntu`即可进入系统。



[^method]: [CSDN: ubuntu启动盘修复grub引导](https://blog.csdn.net/kevin_1996/article/details/124086483)