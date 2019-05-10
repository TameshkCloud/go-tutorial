# Golang Installation
![Gopher jigsaw](jigsaw.png)

 * [How To Install Go on Ubuntu 18.04](#install-go-on-ubuntu)
 * [How To Install Go on MacOS](#install-go-on-macos)
 * [Hello World for testing](#hello-world-in-golang)

## How To Install Go on Ubuntu 18.04

### Step 1 – Install Go on Ubuntu
Login to your Ubuntu system using ssh and upgrade to apply latest security updates there.

```bash
sudo apt-get update
sudo apt-get -y upgrade
```

Now download the Go language binary archive file using following link. To find and download latest version available or 32 bit version go to official download page.

```bash
wget https://dl.google.com/go/go1.12.2.linux-amd64.tar.gz
```

Now extract the downloaded archive and install it to the desired location on the system. For this tutorial, I am installing it under /usr/local directory. You can also put this under the home directory (for shared hosting) or other location.

```bash
$ sudo tar -xvf go1.12.2.linux-amd64.tar.gz
$ sudo mv go /usr/local
```

### Step 2 – Setup Go Environment
Now you need to setup Go language environment variables for your project. Commonly you need to set 3 environment variables as `GOROOT`, `GOPATH` and `PATH`.

Open your `.profile`file and add global variable as follow at the end of the file. You may want to add this into `~/.zshrc` or `~/.bashrc` file as per your shell configuration.


`GOROOT` is the location where Go package is installed on your system.

```bash
export GOROOT=/usr/local/go
```

`GOPATH` is the location of your work directory. For example my project directory is ~/go .

```bash
export GOPATH=$HOME/go
```

Now set the PATH variable to access go binary system wide.

```bash
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
```

All the above environment will be set for your current session only. To make it permanent add above commands in ~/.profile file.

Now, update current shell session.

``` bash 
source ~/.profile # if you added variables to /.profile
source ~/.bashrc # if you added variables to /.bashrc
source ~/.zshrc # if you added variables to /.zshrc
```


### Step 3 – Verify Installation
At this step, you have successfully installed and configured go language on your system. First, use the following command to check the Go version.

``` bash
go version
# go version go1.12.2 linux/amd64
```

Now also verify all configured environment variables using following command.

``` bash
$ go env

GOARCH="amd64"
GOBIN=""
GOCACHE="/root/.cache/go-build"
GOEXE=""
GOHOSTARCH="amd64"
GOHOSTOS="linux"
GOOS="linux"
GOPATH="/root/Projects/Proj1"
GORACE=""
GOROOT="/usr/local/go"
GOTMPDIR=""
GOTOOLDIR="/usr/local/go/pkg/tool/linux_amd64"
GCCGO="gccgo"
CC="gcc"
CXX="g++"
CGO_ENABLED="1"
...
...
```


## How To Install Go on MacOS
It's similar to Ubuntu but some minor differences...

### Step 1 - Remove the Old Installation of Go (if you have it)

```
$ sudo rm -rfv /usr/local/go
```

### Step 2 - Download and install Go

```
$ curl -O https://dl.google.com/go/go1.12.2.linux-amd64.tar.gz
```

Extract the tar archive files into /usr/local (default Go installation directory):

```
$ sudo tar -C /usr/local -xvzf go1.11.3.linux-amd64.tar.gz
```

For a system-wide installation of Go it needs to add the following line at the bottom of /etc/profile file:

``` bash
export PATH=$PATH:/usr/local/go/bin
```

Set `GOPATH`, `GOBIN` and `PATH` environment variables by adding the following lines at the bottom of your `~/.profile` file (or `~/.zshrc` or `~/.bashrc` file):

``` bash
export GOPATH=$HOME/go
export GOBIN=$GOPATH/bin
export PATH=$PATH:/usr/local/go/bin:$GOBIN
```

Refresh profile:

```bash
$ source $HOME/.profile
```

Verify Golang installation by checking the Go version and environment:

```bash
$ go version
$ go env
```

## Hello World for testing

Create $GOPATH/src directory:

```bash
$ mkdir -p $GOPATH/src
```

Create $GOPATH/src/hello.go file with the following contents:

``` go
package main
import "fmt"
func main() {
    fmt.Printf("Hello World!\n")
}
```

Run `go install` to compile and install our “Hello World!” program on Go:

```bash 
$ go install $GOPATH/src/hello.go
```

Execute hello to run the program:

```bash
$ hello
# Hello World!
```
If the program returns “Hello World!”, then Go is successfully installed and functional.