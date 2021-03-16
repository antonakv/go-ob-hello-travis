# golang - travis test that check for hello (travis run green build)
## Intro

This manual is dedicated to run hello.go script.

Tested on Mac OS X.

## Requirements

- Golang installed 
[Golang installation manual](https://golang.org/doc/install)

## Preparation 

- Clone git repository. 

```bash
git clone https://github.com/antonakv/go-ob-hello-travis.git
```

Expected command output looks like this:

```bash
$ git clone https://github.com/antonakv/go-ob-hello-travis.git
Cloning into 'go-ob-hello-travis'...
remote: Enumerating objects: 11, done.
remote: Counting objects: 100% (11/11), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 11 (delta 0), reused 6 (delta 0), pack-reused 0
Receiving objects: 100% (11/11), done.
```

- Change folder to go-ob-hello-travis

```bash
cd go-ob-hello-travis
```

## Build

- In the same folder you were before run 
```bash
make
```

Expected output:
```bash
$ make
go build hello.go
```

## Run

- In the same folder you were before run 
```bash
./hello
```

Expected output:
```bash
$ ./hello
hello
```