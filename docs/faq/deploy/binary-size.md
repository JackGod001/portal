# 减小部署文件大小

## 如何减小 go-zero 编译后二进制文件的大小？

如果未使用 `Kubernetes` 的服务发现，可以在编译的时候使用 `-tags no_k8s` 来排除 `k8s` 相关的依赖包。

具体做法如下：

`GOOS=linux GOARCH=amd64 go build -ldflags="-s -w" -tags no_k8s demo.go`

可以减少超过 20MB 的体积，如下图所示：

![binary-size](/img/content/reduce-binary-size.jpg)

> go-zero 版本：>= v1.7.1
