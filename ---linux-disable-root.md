# Disable Root Login
## TASK:
**After doing some security audits of servers, xFusionCorp Industries security team has implemented some new security policies. One of them is to disable direct root login through SSH.**

>  a. Disable direct SSH root login on *`all app servers`* in Stratos Datacenter.  

## SOLUTION:
> a. In new terminal connect to app1 host:
```
ssh tony@172.16.238.10
```
> b. Make me root:
```
sudo su
```
>c. Disable root access via ssh:
```
sed -i 's/^#PermitRootLogin yes/PermitRootLogin no/' /etc/ssh/sshd_config
```
>d. Restart the service:
```
systemctl restart sshd
```

**Do it for all app servers**
