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

# Crating a testpod
```
oc create ns testspace
oc run testpod --image quay.io/sfhassan/newtools --namespace testspace --labels app=xrd  -- /bin/sh -c "while true; do echo Hello; sleep 10; done" 
```
