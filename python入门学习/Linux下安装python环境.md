

<h3 id="IJoql">**<font style="color:rgb(51, 51, 51);">说明：本文使用的Centos7环境</font>**</h3>
<font style="color:rgb(51, 51, 51);">有时候我们的项目需要在linux下运行，Linux自带的是python2，所以要重新安装python3环境，切记不能动原有的python2环境（linux系统运行依赖该环境）。</font>

<h3 id="FU63y">**<font style="color:rgb(51, 51, 51);">1.查看当前python环境版本</font>**</h3>
python --version

![](https://cdn.nlark.com/yuque/0/2022/png/25700096/1667552726321-8685ceda-42b8-431b-8497-d2d71b85734f.png)<font style="color:rgb(51, 51, 51);">;</font>

<h3 id="gapPF">**<font style="color:rgb(51, 51, 51);">2.首先安装编译安装时需要的依赖包，编译python源码时，需要一些依赖包，一次安装完毕</font>**</h3>
<font style="color:rgb(0, 0, 0);">yum</font> <font style="color:rgb(0, 0, 0);">install</font> <font style="color:rgb(0, 0, 0);">zlib</font><font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">devel</font> <font style="color:rgb(0, 0, 0);">bzip2</font><font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">devel</font> <font style="color:rgb(0, 0, 0);">openssl</font><font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">devel</font> <font style="color:rgb(0, 0, 0);">ncurses</font><font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">devel</font> <font style="color:rgb(0, 0, 0);">sqlite</font><font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">devel</font> <font style="color:rgb(0, 0, 0);">readline</font><font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">devel</font> <font style="color:rgb(0, 0, 0);">tk</font><font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">devel</font> <font style="color:rgb(0, 0, 0);">gcc</font> <font style="color:rgb(0, 0, 0);">make</font> <font style="color:rgb(0, 0, 0);">libffi</font><font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">devel</font>

<font style="color:rgb(51, 51, 51);">复制</font>

<h3 id="fXhd9">**<font style="color:rgb(51, 51, 51);">3.根据需要下载对应的Python版本：</font>**</h3>
[服务器](https://cloud.tencent.com/product/cvm?from=10680)<font style="color:rgb(51, 51, 51);">下载较慢时，可以在官网下载到本地之后，再上传到服务器。</font>

[https://www.python.org/ftp/python/3.7.2/](https://www.python.org/ftp/python/3.7.2/)

<font style="color:rgb(0, 0, 0);">wget</font> <font style="color:rgb(0, 0, 0);">https</font>:<font style="color:rgb(170, 85, 0);">//www.python.org/ftp/3.7.0/Python-3.7.2.tgz</font>

<font style="color:rgb(51, 51, 51);">复制</font>

<h3 id="hDTVI">**<font style="color:rgb(51, 51, 51);">4.解压python安装包</font>**</h3>
<font style="color:rgb(0, 0, 0);">cd</font> <font style="color:rgb(0, 0, 0);">opt</font>  
<font style="color:rgb(0, 0, 0);">tar</font> <font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">zxvf</font> <font style="color:rgb(0, 0, 0);">Python</font><font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(17, 102, 68);">3.7.2</font>.<font style="color:rgb(0, 0, 0);">tgz</font>

<font style="color:rgb(51, 51, 51);">复制</font>

<h3 id="Q6jxz">**<font style="color:rgb(51, 51, 51);">5.新建一个python3的安装目录</font>**</h3>
<font style="color:rgb(0, 0, 0);">mkdir</font> <font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">p</font> <font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">usr</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">local</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">python3</font>

<font style="color:rgb(51, 51, 51);">复制</font>

<h3 id="cUldL">**<font style="color:rgb(51, 51, 51);">6.编译安装</font>**</h3>
<font style="color:rgb(0, 0, 0);">cd</font> <font style="color:rgb(0, 0, 0);">Python</font><font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(17, 102, 68);">3.7.2</font><font style="color:rgb(152, 26, 26);">/</font>  
.<font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">configure</font> <font style="color:rgb(152, 26, 26);">--</font><font style="color:rgb(0, 0, 0);">prefix</font><font style="color:rgb(152, 26, 26);">=</font><font style="color:rgb(255, 85, 0);">/usr/</font><font style="color:rgb(0, 0, 0);">local</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">python3</font>  
<font style="color:rgb(0, 0, 0);">make</font> <font style="color:rgb(152, 26, 26);">&&</font> <font style="color:rgb(0, 0, 0);">make</font> <font style="color:rgb(0, 0, 0);">install</font>

<h3 id="OppXD">**<font style="color:rgb(51, 51, 51);">7.添加软连接</font>**</h3>
<font style="color:rgb(0, 0, 0);">ln</font> <font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">s</font> <font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">usr</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">local</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">python3</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">bin</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">python3</font> <font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">usr</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">bin</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">python3</font>  
<font style="color:rgb(0, 0, 0);">ln</font> <font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">s</font> <font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">usr</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">local</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">python3</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">bin</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">pip3</font> <font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">usr</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">bin</font><font style="color:rgb(152, 26, 26);">/</font><font style="color:rgb(0, 0, 0);">pip3</font>

<font style="color:rgb(51, 51, 51);">复制</font>

<h3 id="dEx2R">**<font style="color:rgb(51, 51, 51);">8.验证是否安装成功</font>**</h3>
<font style="color:rgb(0, 0, 0);">python3</font> <font style="color:rgb(152, 26, 26);">--</font><font style="color:rgb(0, 0, 0);">version</font>  
<font style="color:rgb(0, 0, 0);">pip3</font> <font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">V</font>  
  
  
<font style="color:rgb(0, 0, 0);">pip3</font> <font style="color:rgb(0, 0, 0);">install</font> <font style="color:rgb(0, 0, 0);">xxx</font> <font style="color:rgb(152, 26, 26);">-</font><font style="color:rgb(0, 0, 0);">y</font>

**<font style="color:rgb(51, 51, 51);">9.加入环境变量</font>**

[root@localhost bin]<font style="color:rgb(170, 85, 0);"># vim /etc/profile.d/python.sh </font>  
  
<font style="color:rgb(119, 0, 136);">export</font> <font style="color:rgb(0, 0, 255);">PATH</font><font style="color:rgb(152, 26, 26);">=</font><font style="color:rgb(0, 0, 255);">$PATH</font>:/usr/local/python3/bin/  


  
 

