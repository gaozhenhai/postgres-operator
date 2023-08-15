# Build Images

### build bundle image

```
root@podman:~# cd bundle
root@podman:~# docker build -t 172.22.50.227/system_containers/postgres-operator-bundle:0.1.4 .
root@podman:~# docker push 172.22.50.227/system_containers/postgres-operator-bundle:0.1.4
```

### build registry image
opm 构建 `registry` 镜像时需要 pull 镜像，可以修改本地的 hosts 文件，设置 `dev-registry.tenxcloud.com` 地址为 `harbor` 的地址

```
root@podman:~# opm --skip-tls index add --bundles dev-registry.tenxcloud.com/system_containers/postgres-operator-bundle:0.1.4 --tag dev-registry.tenxcloud.com/system_containers/daas-postgres-registry:0.1.4 -c="docker"

root@podman:~# docker tag dev-registry.tenxcloud.com/system_containers/daas-postgres-registry:0.1.4 172.22.50.227/system_containers/daas-postgres-registry:0.1.4

root@podman:~# docker push 172.22.50.227/system_containers/daas-postgres-registry:0.1.4
```
