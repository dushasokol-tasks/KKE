# Selinux Installation
## TASK:
**The xFusionCorp Industries security team recently did a security audit of their infrastructure and came up with ideas to improve the application and server security. They decided to use SElinux for an additional security layer. They are still planning how they will implement it; however, they have decided to start testing with app servers, so based on the recommendations they have the following requirements:**

>  Install the required packages of SElinux on *`App server 3`* in Stratos Datacenter and disable it permanently for now; it will be enabled after making some required configuration changes on this host. Don't worry about rebooting the server as there is already a reboot scheduled for tonight's maintenance window. Also ignore the status of SElinux command line right now; the final status after reboot should be *`disabled`*.

## SOLUTION:
> a. In new terminal connect to app1 host:
```
ssh banner@172.16.238.12
```
> b. Make me root:
```
sudo su
```
>c. Install selinux:
```
yum install -y policycoreutils policycoreutils-python selinux-policy selinux-policy-targeted libselinux-utils setroubleshoot-server setools setools-console mcstrans
```
>d. Change selinux config:

*'sed' will broke symlink /etc/sysconfig/selinux -> ../selinux/config 
**we need to write /etc/selinux/config instead /etc/sysconfig/selinux**
```
sed -i 's/^SELINUX=enforcing/SELINUX=disabled/' /etc/selinux/config
```
>e. Check status:
```
getenforce; sestatus
```