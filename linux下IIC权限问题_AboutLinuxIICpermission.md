# linux下外设必须用管理员权限打开

## 解决办法： 设置udev规则,将外设权限授权给某个用户组，并将用户加入改组
## 步骤
  1. udev 规则添加 /etc/udev/rule.d/xxxx.rule

  SUBSYSTEM=="input", GROUP="input", MODE="0660"  
  SUBSYSTEM=="i2c-dev", GROUP="i2c", MODE="0660"  
  SUBSYSTEM=="spidev", GROUP="spi", MODE="0660"  
  2. sudo gpasswd -a username i2c
