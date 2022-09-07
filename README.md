# What

This is configuration for Unbound, /etc/resolv.conf and Systemd that is intended to be bundled with https://github.com/buggysolid/unbound-install

Unbound features enabled.

- QNAME minimisation
- Prefetching
- Stale caching
- Minimal responses
- DNSSEC

*This will enable Unbound to come up with your operating system via Systemd. Installation will disable systemd-resolverd.*

# Install

apt-get based systems with systemd (Ubuntu/Debian)

```
sudo apt-get install git -y
git clone https://github.com/buggysolid/unbound-install
cd unbound-install
sudo ./install-apt-get.sh
```

yum/dnf based systems with systemd (Centos/Fedora/Redhat)

```
sudo yum install git -y
git clone https://github.com/buggysolid/unbound-install
cd unbound-install
sudo ./install-yum.sh
```
