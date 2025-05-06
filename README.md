# MyFirstRepository
My First repository for practice


## Connect GitHub and Local Git via SSH

## ✅ 1. Check for Existing SSH Keys

open git bash application

```bash
ls -al ~/.ssh
```
if there are no SSH key-pair available you get below output.
```
ls: cannot access '/c/Users/venga/.ssh': No such file or directory
```
if there are SSH key-pair available you will get below output.
Look for files like `id_rsa` and `id_rsa.pub` or you will get something like below.
```
total 24
drwxr-xr-x 1 venga 197609    0 May  6 18:49 ./
drwxr-xr-x 1 venga 197609    0 May  6 18:49 ../
-rw-r--r-- 1 venga 197609 3389 May  6 18:49 id_rsa
-rw-r--r-- 1 venga 197609  751 May  6 18:49 id_rsa.pub
```

---

## ✅ 2. Generate a New SSH Key

Replace the email with your GitHub email address.

```bash
ssh-keygen -t rsa -b 4096 -C "vengalreddy2005@gmail.com"
```

Press Enter to accept the default file location. You can optionally set a passphrase.

---
go to to file location ; by default you can find the ssh key pair in 
- C:\Users\venga
  -  C:\Users\venga\\.ssh
    -  C:\Users\venga\\.ssh\id_rsa
    -  C:\Users\venga\\.ssh\id_rsa.pub

open `C:\Users\venga\\.ssh\id_rsa.pub` file in notepad and copy entire content

## ✅ 4. Add the Public Key to GitHub

1. Go to github setting and click on SSH and GPG keys
2. Click **"New SSH key"**
3. A form will open
4. in the form enter **title** generally a identification for the ssh key belongs to which system
5. keep **key type** as Authentication key
6. Paste the copied content form id_rsa.pub file in the **Key** text field
7. Finally Click on **add SSH key** button
---

## ✅ 5. Test the SSH Connection
open git bash and run below command to check the connectivity.
```bash
ssh -T git@github.com
```
If the terminal prompt with `Are you sure you want to continue connecting (yes/no/[fingerprint])? `, enter **yes** and press enter key.

Expected output if prompted for confirmation:
```
The authenticity of host 'github.com (20.207.73.82)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
Hi vengalreddy422! You've successfully authenticated, but GitHub does not provide shell access.
```
Expected output if not prompted for confirmation:
```
Hi vengalreddy422! You've successfully authenticated, but GitHub does not provide shell access.
```

---

## ✅ 6. Use SSH to Clone or Connect Repos

### Clone with SSH

```bash
git clone git@github.com:username/repo-name.git
```

### Change Remote to SSH

For existing repositories:

```bash
git remote set-url origin git@github.com:username/repo-name.git
```

---
