---

layout:     post

title:      "Git"

subtitle:   " Configure for Git "

date:       2018-10-10 20:42:00

author:     "Zz"

header-img: "img/default-bg.jpeg"

catalog: true

tags:

    - git

---

git|

## SSH connect

```
ssh root@[IP]:[Port]
```

## Install Git

```
#CentOS
yum -y install git
```

## Add User

```
#change passwd
passwd root
adduser git
passwd git
su git
```

## Create repo

```
cd ~
git init --bare xxx.git
```

## SSH

**Client**

```
#if no .ssh/ or no id_rsa.pub in .ssh/
ssh-keygen
cd .ssh/
scp -P [Port] id_rsa.pub git@[IP]:/home/git/
```

**Server**

```
#if no .ssh/ or no id_rsa.pub in .ssh/
ssh-keygen
cd .ssh/
cat id_rsa.pub >> ~/.ssh/authorized_keys
```

## Git

```
git clone ssh://git@[IP]:[Port]/home/git/xxx.git
```













