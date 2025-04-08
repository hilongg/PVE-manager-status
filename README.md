# shell脚本：
## 一键给PVE添加CPU频率和各种温度显示，NVME硬盘，机械硬盘，固态硬盘信息：



![image](https://github.com/hilongg/PVE-manager-status/blob/main/status.jpg)


## 🌍安装方法

#### 运行以下命令下载并执行脚本：
```bash
(curl -Lf -o /tmp/temp.sh https://raw.githubusercontent.com/hilongg/PVE-manager-status/main/showtempcpufreq.sh || curl -Lf -o /tmp/temp.sh https://ghfast.top/https://raw.githubusercontent.com/hilongg/PVE-manager-status/main/showtempcpufreq.sh) && chmod +x /tmp/temp.sh && /tmp/temp.sh remod
```
<br>

#### 没有显示功耗的，请执行下面的命令安装依赖，请确保安装成功，就是最后的一行的输出，必须为 “成功!” 才表示安装成功了。
```bash
apt update ; apt install linux-cpupower && modprobe msr && echo msr > /etc/modules-load.d/turbostat-msr.conf && chmod +s /usr/sbin/turbostat && echo 成功！
```
<br>

#### 如果你已经用别人的脚本之类的修改过页面，请先用下面命令先回复官方设置之后，才可以运行本脚本：
```bash
apt update
apt install --reinstall pve-manager=$(dpkg -l pve-manager | tail -n 1 | awk '{print $3}')
apt install --reinstall proxmox-widget-toolkit=$(dpkg -l proxmox-widget-toolkit | tail -n 1 | awk '{print $3}')
rm -f /usr/share/perl5/PVE/API2/Nodes.pm*bak
rm -f /usr/share/pve-manager/js/pvemanagerlib.js*bak
rm -f /usr/share/javascript/proxmox-widget-toolkit/proxmoxlib.js*bak
```
<br>

#### 另外：每次pve升级之后都需要执行一次脚本，因为升级后PVE会自己还原文件
