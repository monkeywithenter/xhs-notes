# WSL2/Linux系统更换软件源

以 `Ubuntu24.04` 系统为例

1. 管理员权限备份原有源列表
```
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
```
2. 管理员权限进入vim编辑模式换源文件
```
vim /etc/apt/sources.list.d/ubuntu.sources
```
3. 替换对应源配置，提供包括阿里云(aliyun)和清华(tsinghua)镜像源
阿里云镜像源：
```
# aliyun
Types: deb
URIs: https://mirrors.aliyun.com/ubuntu/
Suites: noble noble-security noble-updates noble-proposed noble-backports
Components: main restricted universe multiverse
Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg
```
清华镜像源：
```
# aliyun
Types: deb
URIs: https://mirrors.tuna.tsinghua.edu.cn/ubuntu/
Suites: noble noble-security noble-updates noble-proposed noble-backports
Components: main restricted universe multiverse
Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg
```
4. 退出vim编辑模式
```
# 按一下 esc 后输入
:x
```
5. 更新软件包列表
```
sudo apt update
```