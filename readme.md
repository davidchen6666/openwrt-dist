# OpenWRT dist for PassWall
[![](https://github.com/davidchen6666/openwrt-dist/workflows/Openwrt%20Build%20Bot/badge.svg)](https://github.com/davidchen6666/openwrt-dist/actions)

This project is only for OpenWRT routers installed for MI AC2100 (OpenWrt official releases). Currently it's based on version 2102.

[You may want original project here.](http://openwrt-dist.sourceforge.net)

## Openwrt Package Builder

### Usage
The build job will upload artifacts in its final step and you can download to your PC.

You then install them in LuCI or upload these downloaded files to your router with SCP/SFTP, then login to your router and use opkg to install these ipk files.

Notes:
> 1) Open up the ipk file (using tools like unzip viewer) for luci-app-passwall and find all the dependencies from the metada files, make sure that they are either in the reposiroty or in your built artifacts;
> 2) Delete dnsmasq first before installing everything, this package will install dnsmasq-full
> 3) The dependency list does not include luci-compat, however if you see any error like not finding 'luci-cbi-datatypes' when installing passwall, you may need to install luci-compat first and then force re-install of passwall

## Build it yourself
[Check here](https://github.com/davidchen6666/openwrt-dist/blob/master/.github/workflows/main.yml)

You need to make a fork and chage items in the matrix yourself to match your needs. If you need to keep your packages safe, please use `usign` to regenerate private key and make the repo private.

## License
GPLv3
