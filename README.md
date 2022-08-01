# SSH-Handshake
### What is SSH Handshake?
Secure Shell (SSH) is a widely used Transport Layer Protocol to secure connections between clients and servers. SSH handshake is a process in the SSH protocol responsible for negotiating initial trust factors for establishing a secure channel between an SSH client and SSH server for an SSH connection. The handshake process includes:

1. SSH protocol version exchange
2. Key Exchange
3. Elliptic Curve Diffie-Hellman Initialization
4. Elliptic Curve Diffie-Hellman Reply
5. New Keys

More about SSH Handshake Ref :- https://goteleport.com/blog/ssh-handshake-explained/

### We are going to connect from server1 to server2 as mark user on server1 to steve on server2

mark user from server1 is connecting to server2 steve user using ssh

### Server 1 setup

step 1: create a user "mark" 
```sh 
$ sudo useradd mark
```
step 2: set a password 
```ssh
$ sudo passwd mark
```
step 3: Login as "mark"

step 4: Generate ssh keys using ```sh ssh-keygen ```  - (do not enter anything - default)

step 5: ssh-copy-id steve@server2publicip

step 6: This will ask for password of steve.

step 7: Enter the password

step 8: Give you a message the one key copied

step 9: If this gives error, then 

step 10: copy your public key and paste it in authorized_keys file in steve's .ssh folder

### Server 2 setup 

step 1: create a user "steve" 
```sh 
$ sudo useradd steve
```
step 2: set a password 
```ssh
$ sudo passwd steve
```
step 3: Login as "steve"

### Manual Process

step 4: ssh-keygen ( .ssh)

step 5: cd .ssh

step 6: vi authorized_keys 

step 7: Insert mode

step 8: Paste the mark id_rsa.pub key

step 9: set permission to authorized_keys (If your owner permissions are not set)

```sh 
$ sudo chmod 664 /home/steve/.ssh/authorized_keys
```

###
This step in server 1 

```sh
[mark@ip-177-32-98-91 ~] $ ssh steve@ipaddressOfstevepublicIP
```
 
