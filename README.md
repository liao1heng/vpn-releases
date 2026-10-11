# Personal VPN 客户端

下载：[公开 Releases](https://github.com/liao1heng/vpn-releases/releases)。首次版本 v0.1.0 为预发布版。选择 macOS Apple Silicon（arm64）或 Windows 10/11 x64；Intel Mac 和 Windows ARM 不在本次交付范围。无需安装 Go。

## 安装前授权

本服务仅供已获管理员授权的设备使用。下载本身不授予 VPN 访问权限；服务密码也不替代设备注册。联系管理员完成本设备注册，私钥在当前设备生成并留在本机，取得独立的 device.json 配置。不要与其他设备共用配置，也不要把私钥、设备配置或控制 token 上传到 GitHub。

管理员登记工具不随公开包提供，普通用户不需要服务器 SSH 账号或密码。解压到新的目录，管理员按私有项目流程完成授权后，再安装客户端。

## macOS arm64

在解压目录执行，配置目录必须已含本设备的 device.json：

```bash
sudo bash install-macos.sh "$HOME/Library/Application Support/personal-vpn" "$USER"
```

将“打开 Personal VPN.terminal”复制到桌面后双击。原生入口固定 Menlo 9pt、56列×9行；支持最小52×9。管理员完整升级会更新后台，界面文件可独立更新。安装保留已有设备、授权和白名单。

## Windows x64

在解压目录的管理员 PowerShell 执行，配置目录必须已含本设备的 device.json：

```powershell
.\install-windows.ps1 -HomeDir "$env:LOCALAPPDATA\personal-vpn"
& "$env:ProgramFiles\PersonalVPN\vpn.exe" tui --home "$env:LOCALAPPDATA\personal-vpn"
```

后台以 SYSTEM 计划任务运行，升级保留配置。Windows 脚本、NRPT、驱动及交互尚未实机验收；交叉编译成功不代表实机验证完成。

## 服务密码与操作

首次打开由管理员提供固定服务密码，正确验证后168小时免输；重复打开不顺延有效期。到期不会中断已有后台连接及其自动恢复，下次打开、主动重新连接或后台重启后建立连接需再验证。验证页 Enter 提交、退格修改、Esc/Ctrl+C 退出；取消只关闭界面。

也可运行 `vpn unlock --home 配置目录`，从终端隐藏输入；不接受密码参数。密码错误、后台不可达或授权无法保存均不能通过验证。首次安装必须同时更新后台，旧后台不支持新的验证接口。

首页使用连接按钮，导航包含连接、在线、白名单、记录。q只关闭界面，后台继续；主动断开不自动重连。悬停导航/问号显示浮层，点击或键盘 m/? 固定，Esc收起；1–4切换面板。基础白名单从 GitHub 刷新，本机追加编辑 whitelist.custom.txt，一行一条；含#整行不加载。保存后点“重载TXT”，已有连接需重建。

白名单支持以下格式混写，合并去重最多256条：

```text
example.com
*.example.org
142.250.0.0/15
8.8.8.8
```

IPv4单地址等价于/32；CIDR中的主机位会规范化。IPv6、默认全网段、本机/隧道保留地址及覆盖VPN控制地址的规则会被拒绝。旧版客户端无法加载网段，须用新包完整升级后台后重载TXT；仅更新界面不够。基础列表现包含21条域名与旧VPN的34条IPv4地址/网段。

## 网络行为与校验

只代理白名单域名和明确列出的IPv4地址/网段，其他目标保留原IPv4路径；不自动修改旧VPN、原DNS或hosts。网段按目标IP覆盖其中全部站点，包括共享CDN；只列网段不会为未列出的域名自动增加加密DNS保护。首次启用需要管理员权限禁用整机对外IPv6，退出或停止后台后保持禁用，不自动重启机器。

白名单VPN/DNS不可用时请求失败；网段通过独立防火墙规则防止核心退出后回退直连，断开时保留。Windows守护每60秒刷新出网网卡集合，新网卡出现到下次刷新之间的窗口及旧VPN同网段路由优先级尚未实机验收。域名规则仍有独立DoH、ECH、hosts及缓存等透明接管限制；网段、Windows与UDP/QUIC等未测项不保证完整覆盖。

使用 PACKAGES.sha256 核对压缩包；包内 REVISION 是来源提交号。macOS在下载目录运行 `shasum -a 256 -c PACKAGES.sha256`；Windows用 `Get-FileHash 文件名 -Algorithm SHA256` 对照。第三方组件、许可证及固定上游源码地址见随包 THIRD_PARTY.md 和 sing-box-LICENSE。
