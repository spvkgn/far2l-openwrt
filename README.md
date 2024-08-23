[![build status](https://github.com/spvkgn/far2l-openwrt/actions/workflows/build.yml/badge.svg)](https://github.com/spvkgn/far2l-openwrt/actions/workflows/build.yml) ![version](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/spvkgn/f53cb6c1d56b0eaf40c88d607fc5fef1/raw/far2l-openwrt.json)
# FAR2L OpenWrt repo
```shell
docker run --rm -it --name openwrt openwrt/rootfs /bin/ash --login
```
```shell
cat << "EOF" > /tmp/public.key
untrusted comment: FAR2L OpenWrt repo
RWSQN8IhM8eOpKLTjP7d0EtwiC0sqCIA4ZR0ikojj1IsklUl/JBY42LQ
EOF
```
```shell
opkg-key add /tmp/public.key && \
echo 'src/gz far2l_repo https://spvkgn.github.io/far2l-openwrt/SNAPSHOT/x86_64' >> /etc/opkg/customfeeds.conf && \
mkdir -p /var/lock/ && opkg update && opkg install far2l
```
