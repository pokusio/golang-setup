# golang-setup
When i need Golang on amachine


## Install


### Debian

```bash
export GOVERSION=1.15.6
export GOOS=linux-amd64
export GO_CPU_ARCH=amd64

export DWLD_URI=https://golang.org/dl/go${GOVERSION}.${GOOS}-${GO_CPU_ARCH}.tar.gz

curl -LO https://golang.org/dl/go${GOVERSION}.${GOOS}-${GO_CPU_ARCH}.tar.gz

sudo mkdir -p /usr/local/golang/${GOVERSION}/${GOOS}/${GO_CPU_ARCH}

# --- 
# delete any previous installation

if [ -f /usr/local/go ]; then 
 sudo rm /usr/local/go
fi;

if [ -f /usr/local/golang/${GOVERSION}/${GOOS}/${GO_CPU_ARCH}/go ]; then 
 sudo rm /usr/local/go
fi;

sudo tar -C /usr/local -xzf go1.15.6.linux-amd64.tar.gz

# [/usr/local/golang/${GOVERSION}/${GOOS}/${GO_CPU_ARCH}/go] is a folder, executables are in [/usr/local/golang/${GOVERSION}/${GOOS}/${GO_CPU_ARCH}/go/bin]
sudo ln -s /usr/local/golang/${GOVERSION}/${GOOS}/${GO_CPU_ARCH}/go /usr/local/go

unset GOVERSION
unset GOOS
unset GO_CPU_ARCH

export PATH=$PATH:/usr/local/go/bin


```

