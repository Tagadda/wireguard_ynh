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

