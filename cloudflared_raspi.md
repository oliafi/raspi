# How to install Argo Tunnel (cloudflared) on Raspberry Pi

Currently, there are packages for only the following architecture types: 

* amd64 / x86-64 
* x86 (32-bit)   
* ARMv6

The Raspberry Pi Type 3 has 64-bit CPU, but its architecture is not arm64 but armhf(arm hard float).

   `dpkg --print-architecture armhf`


##Install cloudflared

###1. Clone the source files from the github  https://github.com/cloudflare/cloudflared to your GOPATH
   
   `git clone https://github.com/cloudflare/cloudflared.git`


###2. Build cloudflared

   `make cloudflared`

###3. Run go install (it will also runs go build)

   `go install github.com/cloudflare/cloudflared/cmd/cloudflared`


##Dependencies

###Golang

If already installed old golang with apt-get:
```
   sudo apt remove golang
   sudo apt-get autoremove
   source [.profile]
```
Then, install Golang 1.9:
```
   wget https://storage.googleapis.com/golang/go1.9.linux-armv6l.tar.gz
   sudo tar -C /usr/local -xzf go1.9.linux-armv6l.tar.gz
   export PATH=$PATH:/usr/local/go/bin # put into your bash profile
```