# WireGuard pour YunoHost

[![Niveau d'intégration](https://dash.yunohost.org/integration/wireguard.svg)](https://dash.yunohost.org/appci/app/wireguard) ![](https://ci-apps.yunohost.org/ci/badges/wireguard.status.svg) ![](https://ci-apps.yunohost.org/ci/badges/wireguard.maintain.svg)  
[![Installer WireGuard avec YunoHost](https://install-app.yunohost.org/install-with-yunohost.svg)](https://install-app.yunohost.org/?app=wireguard)

*[Read this readme in english.](./README.md)*
*[Lire ce readme en français.](./README_fr.md)*

> *Ce package vous permet d'installer WireGuard rapidement et simplement sur un serveur YunoHost.
Si vous n'avez pas YunoHost, regardez [ici](https://yunohost.org/#/install) pour savoir comment l'installer et en profiter.*

## Vue d'ensemble

Réseaux Privés Virtuels (VPN) via WireGuard, avec une web UI pour faciliter sa configuration

**Version incluse :** 2.0~ynh1



## Captures d'écran

![](./doc/screenshots/screenshot.png)

## Avertissements / informations importantes

* Cette application ajoutera un module DMKS à votre noyau Linux.
  * Vous devriez redémarrer votre serveur pour que WireGuard puisse se lancer.
* Cette application inclut WireGuard et une interface web non-officielle pour le configurer.
  * Évitez de modifier les fichiers de configuration via la ligne de commande.
* Utilisez le panneau de permissions de YunoHost pour autoriser des utilisateurs à accéder à WireGuard UI.

### Partagez votre connexion Internet via WireGuard

#### Activez le *port forwarding*

```bash
sudo nano /etc/sysctl.conf
# Décommentez les lignes suivantes :
net.ipv4.ip_forward = 1
net.ipv6.conf.all.forwarding = 1
# Sauvegardez et quittez (CTRL+O, CTRL+X)
sudo sysctl -p
```

Vous pourriez avoir besoin de remplacer `eth0` par l'interface connectée à Internet dans les scripts Post Up et Post Down de `/etc/wireguard/wg0.conf`

## Documentations et ressources

* Site officiel de l'app : https://www.wireguard.com/
* Dépôt de code officiel de l'app : https://github.com/ngoduykhanh/wireguard-ui
* Documentation YunoHost pour cette app : https://yunohost.org/app_wireguard
* Signaler un bug : https://github.com/YunoHost-Apps/wireguard_ynh/issues

## Informations pour les développeurs

Merci de faire vos pull request sur la [branche testing](https://github.com/YunoHost-Apps/wireguard_ynh/tree/testing).

Pour essayer la branche testing, procédez comme suit.
```
sudo yunohost app install https://github.com/YunoHost-Apps/wireguard_ynh/tree/testing --debug
ou
sudo yunohost app upgrade wireguard -u https://github.com/YunoHost-Apps/wireguard_ynh/tree/testing --debug
```

**Plus d'infos sur le packaging d'applications :** https://yunohost.org/packaging_apps