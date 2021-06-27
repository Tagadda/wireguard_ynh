<!--
N.B.: This README was automatically generated by https://github.com/YunoHost/apps/tree/master/tools/README-generator
It shall NOT be edited by hand.
-->

# WireGuard for YunoHost

[![Integration level](https://dash.yunohost.org/integration/wireguard.svg)](https://dash.yunohost.org/appci/app/wireguard) ![](https://ci-apps.yunohost.org/ci/badges/wireguard.status.svg) ![](https://ci-apps.yunohost.org/ci/badges/wireguard.maintain.svg)  
[![Install WireGuard with YunoHost](https://install-app.yunohost.org/install-with-yunohost.svg)](https://install-app.yunohost.org/?app=wireguard)

*[Lire ce readme en français.](./README_fr.md)*

> *This package allows you to install WireGuard quickly and simply on a YunoHost server.
If you don't have YunoHost, please consult [the guide](https://yunohost.org/#/install) to learn how to install it.*

## Overview

Virtual Private Networks (VPN) via WireGuard, with a web UI to ease configuration

**Shipped version:** 2.0~ynh1



## Screenshots

![](./doc/screenshots/screenshot.png)

## Disclaimers / important information

* WireGuard for YunoHost will add a DMKS module to your Linux kernel.
  * You may need to reboot your server for WireGuard to be able to start.
* The package includes WireGuard and non-official web UI to configure it.
  * Avoid altering the configuration files via the command line interface, though.
* Use YunoHost permissions panel to allow users to access the web UI.

### Make your server share its Internet connection

#### Enable port forwarding

```bash
sudo nano /etc/sysctl.conf
# Uncomment the following lines:
net.ipv4.ip_forward = 1
net.ipv6.conf.all.forwarding = 1
# Save and quit (CTRL+O, CTRL+X)
sudo sysctl -p
```

You may need to replace `eth0` with the interface connected to the Internet in `/etc/wireguard/wg0.conf` Post Up and Post Down scripts.


## Documentation and resources

* Official app website: https://www.wireguard.com/
* Upstream app code repository: https://github.com/ngoduykhanh/wireguard-ui
* YunoHost documentation for this app: https://yunohost.org/app_wireguard
* Report a bug: https://github.com/YunoHost-Apps/wireguard_ynh/issues

## Developer info

Please send your pull request to the [testing branch](https://github.com/YunoHost-Apps/wireguard_ynh/tree/testing).

To try the testing branch, please proceed like that.
```
sudo yunohost app install https://github.com/YunoHost-Apps/wireguard_ynh/tree/testing --debug
or
sudo yunohost app upgrade wireguard -u https://github.com/YunoHost-Apps/wireguard_ynh/tree/testing --debug
```

**More info regarding app packaging:** https://yunohost.org/packaging_apps