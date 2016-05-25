# Setting up public-key authentication using SSH on a Linux or OS X computer

Run below command in terminal to generate ssh key pair

```
[13:24 ac@localhost ~/.ssh]$ssh-keygen -f ~/.ssh/eofe
Generating public/private rsa key pair.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/ac/.ssh/eofe.
Your public key has been saved in /home/ac/.ssh/eofe.pub.
The key fingerprint is:
SHA256:cBStnMOKLw5HM7wOW4cXbiLeqfa+QKsmQOXF4iilW7k ac@andhra
The key's randomart image is:
+---[RSA 2048]----+
|    .   oo       |
|  .o o .  .      |
| o=.o .o.o       |
|ooo+   o*        |
|oo..=...S.       |
|o.Eo.*..         |
|. * *.=          |
|.+.@.*.          |
|+.+=Oo           |
+----[SHA256]-----+

```
 
 On your favorate editor save the below config file (or update config file) in your ~/.ssh direcotry 
 
 ```
 
[13:27 ac@localhost ~/.ssh]$cat config 
Host eofe4
 HostName eofe4.mit.edu
 IdentityFile ~/.ssh/eofe

Host eofe5
 HostName eofe5.mit.edu
 IdentityFile ~/.ssh/eofe

Host c3ddb
 HostName c3ddb01.mit.edu
 IdentityFile ~/.ssh/c3ddb

```
If you have passphrase set then add the identity before doing ssh. If you didn't set up a passphrase the you can skip the first step. It is recommended to setup passphrase. 
```
# Step:1 
[13:31 ac@localhost ~]$ssh-add .ssh/eofe
Enter passphrase for .ssh/eofe: 
Identity added: .ssh/eofe (.ssh/eofe)
# Step2
[13:32 ac@localhost ~]$ssh eofe4
Last login: Wed May 25 13:28:48 2016 from fw-1-user-net-flrs.cictr.com
[13:32 ac@eofe4 ~]$
```

