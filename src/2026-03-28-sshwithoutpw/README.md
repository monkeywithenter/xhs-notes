# SSH免密登录(Windows to Linux)
这是一个在Windows上使用 Ed25519 生成密钥对以实现目标服务器的 SSH 免密码登录教程

核心流程：在本地 Windows 生成密钥对 → 把公钥复制到目标服务器 → 测试免密连接。

## 🔑生成密钥对
```PowerShell
ssh-keygen -t ed25519 -C "<密钥用户备注>"
```
`<密钥用户备注>`一般建议使用个人邮箱作为备注，便于服务器多密钥管理

执行`Enter`后默认保存到`C:\用户\<你的用户名>\.ssh\id_ed25519`路径下

## 📋复制公钥至剪贴板
```PowerShell
Get-Content $env:USERPROFILE\.ssh\id_ed25519.pub | clip
```
此时已经复制公钥至剪贴板，`ctrl+v`可查看

## 🔄配置公钥至目标服务器
1. 使用密码登录远程服务器:
```PowerShell
ssh <服务器用户>@<服务器IP>
```
2. 创建 .ssh 目录（如果不存在）
```Linux
mkdir -p ~/.ssh
```
3. 设置目录权限（仅当前用户可访问）
```Linux
chmod 700 ~/.ssh
```
4. 追加公钥至认证文件
```Linux
cat >> ~/.ssh/authorized_keys
```
随后`鼠标右键`或`Ctrl + V`粘贴复制公钥，然后按键盘`Enter`确认，最后`Ctrl + D`结束输入

5. 设置认证文件权限 (仅当前用户可读写)
```Linux
chmod 600 ~/.ssh/authorized_keys
```
## ✅测试是否免密SSH
新开一个`PowerShell`终端，重新使用 SSH 测试，无需密码进入服务器证明成功
```PowerShell
ssh <服务器用户>@<服务器IP>
```