# OpenWRT dist for PassWall
[![](https://github.com/davidchen6666/openwrt-dist/workflows/Openwrt%20Build%20Bot/badge.svg)](https://github.com/davidchen6666/openwrt-dist/actions)

This project is only for OpenWRT routers installed for MI AC2100 (OpenWrt official releases). Currently it's based on version 2102.

[You may want original project here.](http://openwrt-dist.sourceforge.net)

## Openwrt Package Builder

### Usage
#### Step 1
First, Add the public key [simonsmh-dist.pub](./simonsmh-dist.pub) which is paired with private key [key-build](./key-build) for building.

```
wget http://cdn.jsdelivr.net/gh/simonsmh/openwrt-dist@master/simonsmh-dist.pub
opkg-key add simonsmh-dist.pub
```

#### Step 2
You can get target branch from distfeeds on your router.

```
# cat /etc/opkg/distfeeds.conf
src/gz openwrt_core https://downloads.openwrt.org/releases/21.02.0/targets/ramips/mt7621/packages
...
```

#### Step 3

##### Option 1
Add the following line to `/etc/opkg/customfeeds.conf`.

```
src/gz simonsmh http://cdn.jsdelivr.net/gh/simonsmh/openwrt-dist@packages/ramips/mt7621
```

Then install whatever you want.

```
opkg update
opkg install ChinaDNS
opkg install luci-app-chinadns
opkg install dns-forwarder
opkg install luci-app-dns-forwarder
opkg install shadowsocks-libev
opkg install luci-app-shadowsocks
opkg install v2ray-plugin
opkg install luci-app-pdnsd
opkg install v2ray-core
opkg install luci-app-v2ray
opkg install luci-app-vlmcsd
...
```

For more detail please check the manifest.

##### Option 2
You can also search and install them in LuCI or upload these downloaded files to your router with SCP/SFTP, then login to your router and use opkg to install these ipk files.


## Build it yourself
[Check here](https://github.com/davidchen6666/openwrt-dist/blob/master/.github/workflows/main.yml)

You need to make a fork and chage items in the matrix yourself to match your needs. If you need to keep your packages safe, please use `usign` to regenerate private key and make the repo private.

## License
GPLv3
