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
