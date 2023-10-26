# Changes to /etc/rsyslog.conf
sudo vi /etc/rsyslog.conf 
## uncomment (or add) the following:
module(load="imudp") # needs to be done just once
input(type="imudp" port="514")

## Add the following  
:syslogtag, isequal, "mytag:"				/var/log/xrd.log

## Restart service and verify
sudo systemctl restart rsyslog.service 
sudo systemctl is-active rsyslog.service 
active
