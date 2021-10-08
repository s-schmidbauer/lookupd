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
* Send an email to stefan [at] schmidbauer.cz with subject `lookupd add [HOST]`
* Pull the repo. Add hosts to lookupd.conf . Submit a merge request on GitHub

## And now?
Download the IP lists and use them for your purposes
```
wget https://lookup.schmidbauer.cz/schmidbauer.cz.ips -O /etc/pf.blocklist.schmidbauer.cz.ips
```

Every minute, lookupd runs and creates fresh files
```
* * * * *       /usr/local/bin/lookupd /var/www/htdocs/lookupd
```

Every hour, a new list is pulled from GitHub
```
@hourly         cd /var/www/htdocs/lookupd/ && git pull && cp lookupd.conf /etc/lookupd.conf
```

### Github
https://github.com/s-schmidbauer/lookupd




