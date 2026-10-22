# 下载版本

## v0.1.0 (2026-10-11)

来源提交：`f81ee1a21e4a3f27bc512ea1a6aa9584bdd27e33`。macOS arm64 / Windows x64，Windows未实机验收。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.0)

## v0.1.1 (2026-10-11)

来源提交：`53499cdf9b7ed77d8b51f8f0f1365c60c19d0235`。macOS arm64 / Windows x64，Windows未实机验收。

已撤回：Windows构建端生成的macOS脚本含CRLF换行。此版本不提供下载，请使用其他可见版本；来源标签保留，不覆盖附件。
## v0.1.2 (2026-10-11)

来源提交：`e2af28b8e61876f0a28ed22bbcc84e638f2efced`。macOS arm64 / Windows x64，Windows未实机验收。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.2)

## v0.1.3 (2026-10-11)

来源提交：`1494d2b9f6e5c4441625e522289ed0208d981470`。macOS arm64 / Windows x64，Windows未实机验收。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.3)

## v0.1.4 (2026-10-11)

来源提交：`43813b2a2aca6f9717f1676d791158308952641b`。macOS arm64 / Windows x64；Windows本机已完成安装包ifconfig.me单域名验收，防火墙关闭，断开恢复原路径。云电脑Google及其他未测边界待验收。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.4)

## v0.1.5 (2026-10-11)

来源提交：`0168ee964f115ec3d08b8052237da5f5e9a04d53`。macOS arm64 / Windows x64；完成代码测试与构建校验，新安装包及Windows独立窗口实机验收待用户完成，不能沿用旧版测试结果。云电脑Google及其他未测边界待验收。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.5)

## v0.1.6 (2026-10-12)

来源提交：`becd2b906bec691691f2d1095f04f9d19a75ca4a`。macOS arm64 / Windows x64 客户端及独立 Windows 离线诊断包；完成代码测试与构建校验，新安装包、诊断程序及Windows独立窗口云电脑实机验收待用户完成。诊断包无需服务密码，只模拟系统准备/TUN路由，带五分钟自动恢复任务；不测试真实VPN握手。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.6)

## v0.1.7 (2026-10-12)

来源提交：`c3e7427f4724897c6b96fa351661810bfad2b529`。macOS arm64 / Windows x64 客户端及独立 Windows 离线诊断包；完成代码测试与构建校验，新安装包、诊断程序及Windows独立窗口云电脑实机验收待用户完成。Windows采用持久注册表设置和实际IPv6出网探测，不再禁用网卡协议绑定。诊断包无需服务密码，带五分钟自动恢复任务；不测试真实VPN握手。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.7)

## v0.1.8 (2026-10-12)

来源提交：`815a09003626a49a571eb94dc29a3fb0fa4b2c5d`。白名单业务改为 TCP443 HTTPS 按需代理，取消自动心跳、保活、探测、在线轮询与自动DNS诊断；空闲显示按需待命。macOS arm64 / Windows x64 客户端及独立 Windows 离线诊断包通过代码测试、构建与摘要校验。实际网络、10分钟空闲抓包、Windows完整安装和Mac验收范围以本版本README为准，不沿用旧版结果。Windows保留IPv6持久注册表，不禁用网卡绑定；后台仅本地检查，外部IPv6探测须用户手动触发。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.8)

## v0.1.9 (2026-10-12)

来源提交：`4358c442c625c95c78d21bf2146be8b0415a5419`。Windows保留云主机系统IPv6，当前用户浏览器系统代理只用IPv4；白名单走按需HTTPS代理，其他网页走原IPv4路径，断开后保留IPv4直连网页代理。旧版独立IPv6任务在完整升级时移除。macOS沿用原全局IPv6禁用。客户端和独立Windows诊断包通过代码测试、构建与摘要校验；云主机实机浏览器、重启和远程控制保持性仍需现场验收。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.9)

## v0.1.10 (2026-10-13)

来源提交：`8402af1532905f0bf54d0f649063ba1b97ddab08`。Windows保留云主机系统IPv6，当前用户浏览器系统代理只用IPv4；白名单走按需HTTPS代理，其他网页走原IPv4路径，断开后保留IPv4直连网页代理。旧版独立IPv6任务在完整升级时移除。macOS沿用原全局IPv6禁用。客户端和独立Windows诊断包通过代码测试、构建与摘要校验；云主机实机浏览器、重启和远程控制保持性仍需现场验收。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.10)

## v0.1.11 (2026-10-13)

来源提交：`8cc1005e2dc568e32273d433d4af62875c27a187`。白名单采用B来源分行，远端与本地域名数及更新时间独立展示，IP/网段另计；手动重载显示加载中、完成或失败沿用缓存，来源摘要固定，规则可滚动。需完整升级后台，旧后台提示升级。Windows保留系统IPv6，采用系统代理的网页只用IPv4；Mac原有网络行为保持。客户端与独立Windows诊断包通过代码测试、构建及附件摘要校验；本版白名单Windows可见窗口、已连接核心重载及Mac完整升级尚未实机验收。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.11)

## v0.1.12 (2026-10-22)

来源提交：`1e3923c7cd07b1caa4ae72b3f95bbfec074fc5c6`。修复Windows重启后本项目代理开关关闭导致启动失败：已有备份且地址、绕过列表、无PAC状态仍匹配时自动恢复，其他代理变更继续拒绝覆盖，保留最初备份。Windows原生构建，并执行Go测试/vet及PowerShell 5隔离注册表回归；公开附件核对SHA256。云电脑完整升级、真实重启及长期运行尚未实机验收，保持预发布。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.12)

## v0.1.13 (2026-10-22)

来源提交：`66829c94ee117379de05a3b46df1aaab894bcd5a`。修复Windows本机5355/UDP被DNS Client等系统组件占用时后台无法启动：由系统分配并同时保留TCP/UDP回环DNS端口，核心使用实际端口，重载复用、退出释放；不修改系统DNS或停止系统服务，macOS仍使用5355。Windows原生构建并执行Go测试/vet、真实回环DNS及端口冲突回归、PowerShell 5隔离注册表回归；公开附件核对SHA256。受影响电脑完整升级、真实业务、重启与长期运行尚未实机验收，保持预发布。

[下载](https://github.com/liao1heng/vpn-releases/releases/tag/v0.1.13)

