## 1 - Installation

For this workshop, you will need the following tools:

- [go](https://go.dev/) - The programming language you'll use during the workshop
- [protoc](https://developers.google.com/protocol-buffers) - The protobuf compiler

Pour ce workshop nous utiliserons golang en association avec grpc-gateway, pour ce faire installer golang:

### **go**
```shell
# Will download go binaries
wget https://go.dev/dl/go1.19.linux-amd64.tar.gz

# Will extract and move binaries into GOPATH
sudo rm -rf /usr/local/go && sudo tar -C /usr/local -xzf go1.19.linux-amd64.tar.gz
```

Then, open your `.zshrc` or `.bashrc` file and append the following line at the end:
```shell
export PATH=$PATH:/usr/local/go/bin:$(go env GOPATH)/bin
```

### **protoc**

protoc is the protocol buffer compiler, you can install it with your package manager:
- under fedora: `sudo dnf install protobuf-compiler`
- under ubuntu: `sudo apt install protobuf-compiler`
- under macos: `brew install protoc`

If you have any issue with the installation, go [here](https://grpc.io/docs/protoc-installation/).

## Init golang project

Create a folder for this workshop and run the following command inside to initialize the go project:
```shell
go mod init grpc-workshop
```

Then run:
```shell
go install \
    github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-grpc-gateway \
    github.com/grpc-ecosystem/grpc-gateway/v2/protoc-gen-openapiv2 \
    google.golang.org/protobuf/cmd/protoc-gen-go \
    google.golang.org/grpc/cmd/protoc-gen-go-grpc```
