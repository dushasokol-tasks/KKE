# TASK:
**There are specific access levels for users defined by the xFusionCorp Industries system admin team. Rather than providing access levels to every individual user, the team has decided to create groups with required access levels and add users to that groups as needed. See the following requirements:**

>  a. Create a group named *`nautilus_sftp_users`* in all App servers in Stratos Datacenter.  
>  b. Add the user *`stark`* to *`nautilus_sftp_users`* in all App servers. (create the user if not present already)

# SOLUTION:
> a. In new terminal connect to app1 host:
```
ssh tony@172.16.238.10
```
> b. Set shell variable:
```
userMe='stark'; groupMe='nautilus_sftp_users';
```
>c. Add new group and create new user as member of this group:
```
sudo groupadd ${groupMe};
sudo useradd -G ${groupMe} ${userMe};
```
>d. Verify:
```
getent passwd | grep  ${userMe};groups ${userMe};
```

**Do it for all app servers**
