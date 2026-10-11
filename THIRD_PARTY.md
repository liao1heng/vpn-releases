# 第三方组件

- sing-box 1.14.3，SagerNet，GPL-3.0-or-later：https://github.com/SagerNet/sing-box/tree/v1.14.3 。分发包包含官方预编译原件，发布资产摘要固定于 configs/core-release.json；源码和许可证可由该固定标签取得。
- tcell/v2、uniseg（Apache/MIT），miekg/dns（BSD），Go x/net、x/text、x/sys（BSD），版本锁定于 go.mod/go.sum。
- WireGuard：服务端使用 Debian wireguard-tools 与内核模块，客户端使用 sing-box 内建成熟 WireGuard 实现；未自行实现密码协议。

发布时保留本文件及官方核心许可证。项目代码与对应构建脚本一并交付。
