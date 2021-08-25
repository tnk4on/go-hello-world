# Go: Hello, World!

## Sample Go code: hello.go

```
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

## How to build a Go code 
Build the source code in a container.
```
$ mkdir hello; cd hello
$ vi hello.go
$ podman pull docker.io/library/golang
$ podman run --rm -v .:/hello:z -w /hello golang go mod init hello
$ podman run --rm -v .:/hello:z -w /hello golang go build
```

Test run the Go binary.
```
$ ls -l
total 1736
-rw-r--r--. 1 user user      22 Aug 21 02:30 go.mod
-rwxr-xr-x. 1 user user 1766198 Aug 21 02:30 hello
-rw-rw-r--. 1 user user      76 Aug 18 03:26 hello.go
$ ./hello
Hello, World!
```

## Go version of container images

### golang
```
$ podman pull docker.io/library/golang
$ podman run --rm golang go version
go version go1.17 linux/amd64
```

### ubi8/go-toolset
```
$ podman pull registry.access.redhat.com/ubi8/go-toolset
$ podman run --rm go-toolset go version
go version go1.15.14 linux/amd64
```

## Reference
- [fatherlinux/ubi-go-toolset-example](https://github.com/fatherlinux/ubi-go-toolset-example)
- [Tutorial: Get started with Go - The Go Programming Language](https://golang.org/doc/tutorial/getting-started)
- [Download and install - The Go Programming Language](https://golang.org/doc/install)