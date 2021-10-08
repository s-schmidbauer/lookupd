# lookupd

## The lookup daemon

* Resolves hostnames and more to IPs - so you don't have to!

## Install
```
doas mkdir -p /var/www/htdocs/lookupd/
doas cp lookupd /usr/local/bin/
doas chmod +x /usr/local/bin/lookupd
```

## Configure
Put some hosts in /etc/lookupd.hosts.conf
```
www.schmidbauer.cz
www.heise.de
www.golem.de
```
Put some TXT records in /etc/lookupd.records.conf
```
_netblocks.google.com
```
Put some URLs to JSON in /etc/lookupd.urls.conf

## Usage
It needs a output directory to write to
`lookupd /var/www/htdocs/lookupd`
where it creates [hostname].ips files

## Want to submit a host / record / URL?
* Send an email to stefan [at] schmidbauer.cz with subject `lookupd add [HOST]`
* Pull the repo. Add line to the appropriate config . Submit a merge request on GitHub

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
@hourly         cd /var/www/htdocs/lookupd/ && /usr/local/bin/git pull && /bin/cp lookupd.conf /etc/lookupd.conf
```

### Github
https://github.com/s-schmidbauer/lookupd

