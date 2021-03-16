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
$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==> default: Importing base box 'aakulov/bionic64'...
==> default: Matching MAC address for NAT networking...
==> default: Checking if box 'aakulov/bionic64' version '21.03.02' is up to date...
==> default: Setting the name of the VM: go-ob-hello-travis_default_1615908031711_66315
==> default: Clearing any previously set network interfaces...
==> default: Preparing network interfaces based on configuration...
    default: Adapter 1: nat
==> default: Forwarding ports...
    default: 22 (guest) => 2222 (host) (adapter 1)
==> default: Booting VM...
==> default: Waiting for machine to boot. This may take a few minutes...
    default: SSH address: 127.0.0.1:2222
    default: SSH username: vagrant
    default: SSH auth method: private key
    default: 
    default: Vagrant insecure key detected. Vagrant will automatically replace
    default: this with a newly generated keypair for better security.
    default: 
    default: Inserting generated public key within guest...
    default: Removing insecure key from the guest if it's present...
    default: Key inserted! Disconnecting and reconnecting using new SSH key...
==> default: Machine booted and ready!
==> default: Checking for guest additions in VM...
==> default: Mounting shared folders...
    default: /vagrant => /Users/aakulov/Documents/Development/Hashicorp/go-ob-hello-travis
==> default: Running provisioner: file...
    default: hello.go => $HOME/hello.go
==> default: Running provisioner: shell...
    default: Running: /var/folders/_d/p7jhkm3n29d8q5mr_7k18yb00000gp/T/vagrant-shell20210316-70155-ahdtiu.sh
    default: Get:1 http://security.ubuntu.com/ubuntu bionic-security InRelease [88.7 kB]
    default: Get:2 https://apt.releases.hashicorp.com bionic InRelease [4,421 B]
    default: Get:3 http://mirrors.ubuntu.com/mirrors.txt Mirrorlist [973 B]
    default: Get:7 http://security.ubuntu.com/ubuntu bionic-security/main i386 Packages [934 kB]
    default: Err:2 https://apt.releases.hashicorp.com bionic InRelease
    default:   The following signatures couldn't be verified because the public key is not available: NO_PUBKEY DA418C88A3219F7B
    default: Get:8 http://security.ubuntu.com/ubuntu bionic-security/main amd64 Packages [1,598 kB]
    default: Get:9 http://security.ubuntu.com/ubuntu bionic-security/main Translation-en [305 kB]
    default: Get:5 http://mirror.eu.kamatera.com/ubuntu bionic-updates InRelease [88.7 kB]
    default: Get:10 http://security.ubuntu.com/ubuntu bionic-security/restricted i386 Packages [17.7 kB]
    default: Get:11 http://security.ubuntu.com/ubuntu bionic-security/restricted amd64 Packages [253 kB]
    default: Get:6 https://mirror.nl.bontekoe.technology/ubuntu bionic-backports InRelease [74.6 kB]
    default: Get:12 http://security.ubuntu.com/ubuntu bionic-security/restricted Translation-en [32.9 kB]
    default: Get:13 http://security.ubuntu.com/ubuntu bionic-security/universe i386 Packages [979 kB]
    default: Hit:4 https://mirror.nl.leaseweb.net/ubuntu bionic InRelease
    default: Get:14 http://mirror.eu.kamatera.com/ubuntu bionic-updates/main i386 Packages [1,237 kB]
    default: Get:15 http://security.ubuntu.com/ubuntu bionic-security/universe amd64 Packages [1,114 kB]
    default: Get:16 http://security.ubuntu.com/ubuntu bionic-security/universe Translation-en [250 kB]
    default: Get:17 http://security.ubuntu.com/ubuntu bionic-security/multiverse amd64 Packages [19.1 kB]
    default: Get:18 http://security.ubuntu.com/ubuntu bionic-security/multiverse i386 Packages [6,480 B]
    default: Get:19 http://security.ubuntu.com/ubuntu bionic-security/multiverse Translation-en [4,412 B]
    default: Get:20 http://mirror.eu.kamatera.com/ubuntu bionic-updates/main amd64 Packages [1,937 kB]
    default: Get:21 http://mirror.eu.kamatera.com/ubuntu bionic-updates/main Translation-en [397 kB]
    default: Get:22 http://mirror.eu.kamatera.com/ubuntu bionic-updates/restricted i386 Packages [24.3 kB]
    default: Get:23 http://mirror.eu.kamatera.com/ubuntu bionic-updates/restricted amd64 Packages [274 kB]
    default: Get:24 http://mirror.eu.kamatera.com/ubuntu bionic-updates/restricted Translation-en [36.5 kB]
    default: Get:25 http://mirror.eu.kamatera.com/ubuntu bionic-updates/universe amd64 Packages [1,720 kB]
    default: Get:26 http://mirror.eu.kamatera.com/ubuntu bionic-updates/universe i386 Packages [1,561 kB]
    default: Get:27 http://mirror.eu.kamatera.com/ubuntu bionic-updates/universe Translation-en [364 kB]
    default: Get:28 http://mirror.eu.kamatera.com/ubuntu bionic-updates/multiverse i386 Packages [11.6 kB]
    default: Get:29 http://mirror.eu.kamatera.com/ubuntu bionic-updates/multiverse amd64 Packages [24.9 kB]
    default: Get:30 http://mirror.eu.kamatera.com/ubuntu bionic-updates/multiverse Translation-en [6,464 B]
    default: Reading package lists...
    default: W
    default: : 
    default: GPG error: https://apt.releases.hashicorp.com bionic InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY DA418C88A3219F7B
    default: E
    default: : 
    default: The repository 'https://apt.releases.hashicorp.com bionic InRelease' is not signed.
    default: Reading package lists...
    default: Building dependency tree...
    default: 
    default: Reading state information...
    default: The following additional packages will be installed:
    default:   squashfs-tools
    default: Suggested packages:
    default:   zenity | kdialog
    default: Recommended packages:
    default:   gnupg
    default: The following NEW packages will be installed:
    default:   snapd squashfs-tools
    default: 0 upgraded, 2 newly installed, 0 to remove and 9 not upgraded.
    default: Need to get 21.2 MB of archives.
    default: After this operation, 103 MB of additional disk space will be used.
    default: Get:1 http://mirrors.ubuntu.com/mirrors.txt Mirrorlist [973 B]
    default: Get:3 http://mirror.nl.datapacket.com/ubuntu bionic-updates/main amd64 snapd amd64 2.48.3+18.04 [21.0 MB]
    default: Get:2 http://nl.archive.ubuntu.com/ubuntu bionic-updates/main amd64 squashfs-tools amd64 1:4.3-6ubuntu0.18.04.1 [110 kB]
    default: dpkg-preconfigure: unable to re-open stdin: No such file or directory
    default: Fetched 21.2 MB in 8s (2,779 kB/s)
    default: Selecting previously unselected package squashfs-tools.
    default: (Reading database ... 
    default: (Reading database ... 5%
    default: (Reading database ... 10%
    default: (Reading database ... 15%
    default: (Reading database ... 20%
    default: (Reading database ... 25%
    default: (Reading database ... 30%
    default: (Reading database ... 35%
    default: (Reading database ... 40%
    default: (Reading database ... 45%
    default: (Reading database ... 50%
    default: (Reading database ... 55%
    default: (Reading database ... 60%
    default: (Reading database ... 65%
    default: (Reading database ... 70%
    default: (Reading database ... 75%
    default: (Reading database ... 80%
    default: (Reading database ... 85%
    default: (Reading database ... 90%
    default: (Reading database ... 95%
    default: (Reading database ... 100%
    default: (Reading database ... 
    default: 100017 files and directories currently installed.)
    default: Preparing to unpack .../squashfs-tools_1%3a4.3-6ubuntu0.18.04.1_amd64.deb ...
    default: Unpacking squashfs-tools (1:4.3-6ubuntu0.18.04.1) ...
    default: Selecting previously unselected package snapd.
    default: Preparing to unpack .../snapd_2.48.3+18.04_amd64.deb ...
    default: Unpacking snapd (2.48.3+18.04) ...
    default: Setting up squashfs-tools (1:4.3-6ubuntu0.18.04.1) ...
    default: Setting up snapd (2.48.3+18.04) ...
    default: Created symlink /etc/systemd/system/multi-user.target.wants/snapd.apparmor.service → /lib/systemd/system/snapd.apparmor.service.
    default: Created symlink /etc/systemd/system/multi-user.target.wants/snapd.autoimport.service → /lib/systemd/system/snapd.autoimport.service.
    default: Created symlink /etc/systemd/system/multi-user.target.wants/snapd.core-fixup.service → /lib/systemd/system/snapd.core-fixup.service.
    default: Created symlink /etc/systemd/system/multi-user.target.wants/snapd.recovery-chooser-trigger.service → /lib/systemd/system/snapd.recovery-chooser-trigger.service.
    default: Created symlink /etc/systemd/system/multi-user.target.wants/snapd.seeded.service → /lib/systemd/system/snapd.seeded.service.
    default: Created symlink /etc/systemd/system/cloud-final.service.wants/snapd.seeded.service → /lib/systemd/system/snapd.seeded.service.
    default: Created symlink /etc/systemd/system/multi-user.target.wants/snapd.service → /lib/systemd/system/snapd.service.
    default: Created symlink /etc/systemd/system/timers.target.wants/snapd.snap-repair.timer → /lib/systemd/system/snapd.snap-repair.timer.
    default: Created symlink /etc/systemd/system/sockets.target.wants/snapd.socket → /lib/systemd/system/snapd.socket.
    default: Created symlink /etc/systemd/system/final.target.wants/snapd.system-shutdown.service → /lib/systemd/system/snapd.system-shutdown.service.
    default: snapd.failure.service is a disabled or a static unit, not starting it.
    default: snapd.snap-repair.service is a disabled or a static unit, not starting it.
    default: Processing triggers for dbus (1.12.2-1ubuntu1.2) ...
    default: Processing triggers for mime-support (3.60ubuntu1) ...
    default: Processing triggers for man-db (2.8.3-2ubuntu0.1) ...
    default: 2021-03-16T15:21:29Z INFO Waiting for automatic snapd restart...
    default: go 1.15.8 from Michael Hudson-Doyle (mwhudson) installed
    default: export GOROOT=/snap/go/current
    default: export PATH=$PATH:/snap/bin:$GOROOT/bin
    default: export GOPATH=~/go
==> default: Running provisioner: shell...
    default: Running: /var/folders/_d/p7jhkm3n29d8q5mr_7k18yb00000gp/T/vagrant-shell20210316-70155-12u74v0.sh
==> default: Running provisioner: shell...
    default: Running: /var/folders/_d/p7jhkm3n29d8q5mr_7k18yb00000gp/T/vagrant-shell20210316-70155-1adi9d7.sh
    default: passed: expected hello got hello
```
