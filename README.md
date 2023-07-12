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

```
cat<<EOF | sudo /usr/bin/env bash
if [[ -f "/usr/bin/apt" ]]; then
  apt update
  apt install -y git
  git clone https://github.com/buggysolid/unbound-install
  cd unbound-install
  sudo ./install-apt-get.sh
elif [[ -f "/usr/bin/yum" ]]; then
  yum makecache
  yum install -y git
  git clone https://github.com/buggysolid/unbound-install
  cd unbound-install
  sudo ./install-yum.sh
else
  echo "Could not determine which package manager is installed."
  exit
fi
EOF
```
