# Linux User Expiry
## TASK:
**A developer Ammar has been assigned Nautilus project temporarily as a backup resource. As a temporary resource for this project, we need a temporary user for Ammar. It’s a good idea to create a user with a set expiration date so that the user won't be able to access servers beyond that point.**

>  Therefore, create a user named *`ammar`* on the *`App Server 1`*. Set expiry date to *`2021-01-28`* in Stratos Datacenter. Make sure the user is created as per standard and is in lowercase.

## SOLUTION:
> a. In new terminal connect to app1 host:
```
ssh tony@172.16.238.10
```
> b. Create user with expiration date:
```
sudo useradd -e 2021-01-28 ammar
```
>c. Check user aging:
```
sudo chage -l ammar
```