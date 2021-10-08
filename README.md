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
where it creates [hostname].ips files

## Want to submit a host?
Send an email to stefan [at] schmidbauer.cz with subject `lookupd add [HOST]`

## And now?
Download the IP lists and use them for your purposes
```
wget https://lookup.schmidbauer.cz/schmidbauer.cz.ips -O /etc/pf.blocklist.schmidbauer.cz.ips
```

### Github
https://github.com/s-schmidbauer/lookupd




