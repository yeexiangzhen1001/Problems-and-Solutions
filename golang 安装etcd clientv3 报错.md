# 报错1
```go
go  get  go.etcd.io/etcd/clientv3
go: finding github.com/coreos/go-systemd/journal latest
go: finding github.com/coreos/go-systemd latest
go: finding github.com/gogo/protobuf v1.2.1
build command-line-arguments: cannot load github.com/coreos/go-systemd/journal: no matching versions for query "latest"
```
# 解决方法
在你项目的go.mod中添加
```go
replace github.com/coreos/go-systemd => github.com/coreos/go-systemd/v22 v22.0.0
```
# 报错2
```go
github.com/coreos/etcd/clientv3/balancer/resolver/endpoint
../../pkg/mod/github.com/coreos/etcd@v3.3.18+incompatible/clientv3/balancer/resolver/endpoint/endpoint.go:114:78: undefined: resolver.BuildOption
../../pkg/mod/github.com/coreos/etcd@v3.3.18+incompatible/clientv3/balancer/resolver/endpoint/endpoint.go:182:31: undefined: resolver.ResolveNowOption
# github.com/coreos/etcd/clientv3/balancer/picker
../../pkg/mod/github.com/coreos/etcd@v3.3.18+incompatible/clientv3/balancer/picker/err.go:37:44: undefined: balancer.PickOptions
../../pkg/mod/github.com/coreos/etcd@v3.3.18+incompatible/clientv3/balancer/picker/roundrobin_balanced.go:55:54: undefined: balancer.PickOptions
```
# 解决方法
在你项目的go.mod中添加
```go
replace google.golang.org/grpc => google.golang.org/grpc v1.26.0
```