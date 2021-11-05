# OpenWRT dist for PassWall
[![](https://github.com/davidchen6666/openwrt-dist/workflows/Openwrt%20Build%20Bot/badge.svg)](https://github.com/davidchen6666/openwrt-dist/actions)

This project is only for OpenWRT routers installed for MI AC2100 (OpenWrt official releases). Currently it's based on version 2102.

[You may want original project here.](http://openwrt-dist.sourceforge.net)

## Openwrt Package Builder

### Usage
The build job will upload artifacts in its final step and you can download to your PC.

You then install them in LuCI or upload these downloaded files to your router with SCP/SFTP, then login to your router and use opkg to install these ipk files.


## Build it yourself
[Check here](https://github.com/davidchen6666/openwrt-dist/blob/master/.github/workflows/main.yml)

You need to make a fork and chage items in the matrix yourself to match your needs. If you need to keep your packages safe, please use `usign` to regenerate private key and make the repo private.

## License
GPLv3
