# Linux Services
## TASK:
**As per details shared by the development team, the new application release has some dependencies on the back end. There are some packages/services that need to be installed on all app servers under Stratos Datacenter. As per requirements please perform the following steps:**

> a. Install *`postfix`* package on *`all the application`* servers.

> b. Once installed, make sure it is enabled to start during boot.

## SOLUTION:
> a. In new terminal connect to app1 host:
```
ssh tony@172.16.238.10
```
> b. Install postfix:
```
sudo yum install -y postfix
```
>c. Enable postfix:
```
sudo systemctl enable postfix
```
**Do it for all app servers**