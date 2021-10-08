# lookupd

## The lookup daemon

* Resolves hostnames to IPs - so you don't have to!
* Use the lists made in blocklists and more

## Install
```
doas mkdir -p /var/www/htdocs/lookupd/
doas cp lookupd /usr/local/bin/
doas chmod +x /usr/local/bin/lookupd
```

## Configure
Put some hosts in /etc/resolvarr.conf
```
www.schmidbauer.cz
www.heise.de
www.golem.de
```

## Usage
It needs a output directory to write to

`lookupd /var/www/htdocs/lookupd`

It creates [hostname].ips files
