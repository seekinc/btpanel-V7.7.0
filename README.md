# btpanel-v7.7.0
btpanel-v7.7.0-backup  官方原版v7.7.0版本面板备份

**Centos/Ubuntu/Debian安装命令 独立运行环境（py3.7）：**
```Bash
curl -sSO https://raw.githubusercontent.com/seekinc/btpanel-v7.7.0/main/install/install_panel.sh && bash install_panel.sh
```
<br/>&nbsp;
**如果你已经安装面板，可以使用离线包来降级：**
```Bash
wget https://raw.githubusercontent.com/seekinc/btpanel-v7.7.0/main/install/src/LinuxPanel-7.7.0.zip
unzip LinuxPanel-7.7.0.zip
cp /root/LinuxPanel-7.7.0/panel /root
cd panel
bash update.sh
cd .. && rm -f LinuxPanel-7.7.0.zip && rm -rf panel
```
<br/>&nbsp;
**跳过登录验证：**
```Bash
sed -i "s|if (bind_user == 'True') {|if (bind_user == 'REMOVED') {|g" /www/server/panel/BTPanel/static/js/index.js
rm -rf /www/server/panel/data/bind.pl
```
<br/>&nbsp;
**如果出现乱码或LC_ALL报错，请修改语言区域：**
```Bash
nano /etc/default/locale
```
```Bash
LANG=en_US.UTF-8
```
***或者直接输入以下命令***
```Bash
localedef -i en_US -f UTF-8 en_US.UTF-8
```
