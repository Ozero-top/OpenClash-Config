## OpenClash YAML运行配置文件 在线生成工具
![image](https://raw.githubusercontent.com/Ozero-top/OpenClash-Online-YAML-Generator/e186374986f00f39fe8ed7b5cb2a654bb2a12c62/Interface%20Preview.png)
## [在线演示地址](https://clash.ovitor.asia/)
用户操作指引
场景 A：配置链式代理（中转 + 静态住宅 IP 落地）
1. 打开网页，选择 【🔲 链式代理 - 独立节点】 或 【📑 链式代理 - 批量粘贴】模式。

2. 输入【输入代理服务商名称】和【中转代理订阅地址】。

3. 选择分流匹配模式：

网段匹配：适用于AP或无线软路由器多 SSID / VLAN 隔离场景。

【指定设备单 IP】：适用于单局域网下为指定局域网IP设备分配专属落地 IP。

4. 设置 【前置中转策略组 (dialer-proxy)】（通常保持默认 所有-手动 或 所有-自动、已做好前置中转的选择直连）。

5. 输入或粘贴落地节点链接，系统会自动识别国家地区（识别出 通用 的，会出现两个情况：1.协议地址网络不通；2.识别错误，手动修改相应地区标识）。

6. 点击 【🚀 生成并自动下载完整 YAML 文件】。

7. clash运行该yaml文件后，无需任何设置即可按照前面 【网段匹配】 或 【指定设备单 IP】配置自动运行（默认全局），可在 Clash 的 [控制面板] 打开 [ZashBoard] 找到策略组的【所有 - 手动】选择延时最低节点作为前置中转

8. 其他策略组对 【网段匹配】 或 【指定设备单 IP】 无任何影响；仅作用于 OpenWRT软路由 非 【网段匹配】 或 【指定设备单 IP】 的设备；可自动分流，WebRTC/DNS防泄漏

（分流/防泄漏前提要自行配置clash插件 或 替换clash插件配置文件，具体操作可参考：[使用指南](https://github.com/Ozero-top/OpenClash-Config/blob/main/OpenClash%E7%B3%BB%E7%BB%9F%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6/%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E.md) 的操作说明 - 【替换OpenClash插件配置文件】 )

场景 B：配置家用自动分流模式（单/双订阅）
1. 选择 【🌐 自动分流 - 家用模式】。

2. 输入主力机场订阅地址；若有备用机场，勾选 **启用备用代理聚合** 并填入备用订阅地址。

3. 点击 【🚀 生成并自动下载完整 YAML 文件】。

4. clash运行该yaml文件后，可在 Clash 的 [控制面板] 打开 [ZashBoard] 找到策略组，根据使用需求自行设置；除 直连、拒绝 策略组，其他策略组均是自动切换最低延时节点；可手动选择，但会在3-6小时后自动切换到延时最低节点

5. 分流/防泄漏前提要自行配置clash插件 或 替换clash插件配置文件，具体操作可参考：[使用指南](https://github.com/Ozero-top/OpenClash-Config/blob/main/OpenClash%E7%B3%BB%E7%BB%9F%E9%85%8D%E7%BD%AE%E6%96%87%E4%BB%B6/%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E.md)的操作说明 - 【替换OpenClash插件配置文件】

场景 C：【Socks5 / SK 格式转换】
1. 选择 【🛠️ Socks5 / SK 格式转换】 模式。

2. 在输入框粘贴 IP|端口|账号|密码 格式的文本（每行一条）。

3. 点击 【⚡ 开始批量转换】，转换完成后点击 【📋 复制转换结果】，可直接用于链式代理模式中。
