# golang - travis test that check for hello (travis run green build)
## Intro
This manual is dedicated to run vagrant box with program that prints hello. 

Tested on Mac OS X.

## Requirements
- Oracle Virtualbox recent version installed
[VirtualBox installation manual](https://www.virtualbox.org/manual/ch01.html#intro-installing)

- Hashicorp vagrant recent version installed
[Vagrant installation manual](https://learn.hashicorp.com/tutorials/vagrant/getting-started-install)

- git installed
[Git installation manual](https://git-scm.com/download/mac)

## Preparation 
- Clone git repository. 

```bash
git clone https://github.com/antonakv/go-ob-hello-travis.git
```

Expected command output looks like this:

```bash
Cloning into 'go-ob-hello-travis'...
remote: Enumerating objects: 12, done.
remote: Counting objects: 100% (12/12), done.
remote: Compressing objects: 100% (12/12), done.
remote: Total 12 (delta 1), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (12/12), done.
Resolving deltas: 100% (1/1), done.
```

- Change folder to go-ob-hello-travis

```bash
cd go-ob-hello-travis
```

## Provisioning

- In the same folder you were before run 

```bash
vagrant up
```

Sample result
```bash

```
