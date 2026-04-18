# VMware Station 虚拟机 + Ubuntu22.04 镜像配置（安装篇）
延续上一篇Mware 虚拟机 + Ubuntu 22.04 镜像配置前的准备篇内容，现在开始正式使用 VMware 安装 Ubuntu 22.04镜像！

## 开始前准备
- 电脑配置：至少 4GB 内存，20GB 空闲硬盘，关闭杀毒软件。
- 虚拟机安装包：`VMware-workstation-full-17.6.2-24409262.exe`
- Linux镜像文件：`ubuntu-22.04.5-desktop-amd64.iso`

## VMware 安装流程
1. 双击打开 VMware 的 `.exe` 后缀安装程序

![alt text](./img/01.png)

2. 勾选接受条款后进入下一步

![alt text](./img/02.png)

3. 勾选 `WHP` 安装后进入下一步

![alt text](./img/03.png)

> `WHP`作为一个兼容补丁，让你的电脑在运行虚拟机的时候也能运行其他Hyper-V服务例如WSL2、docker、Windows沙箱等

4. 指定安装位置后进入下一步

![alt text](./img/04.png)


5. 关闭产品更新以及体验计划后进入下一步

![alt text](./img/05.png)

6. 默认创建后进入下一步

![alt text](./img/06.png)

7. 正式开始安装

![alt text](./img/07.png)

8. 稍作等待

![alt text](./img/08.png)

9. 安装成功

![alt text](./img/09.png)

此时应该可以在桌面上看到VMware的快捷打开方式

## Ubuntu 22.04映像配置流程
1. 双击打开 `VMware Workstation Pro`, 点击 `创建新的虚拟机`

![alt text](./img/10.png)

2. 选择推荐的 `典型` 进行配置后下一步

![alt text](./img/11.png)

3. 选择 `稍后安装操作系统` 后下一步

!![alt text](./img/12.png)

4. `选择客户机操作系统` 按提供的默认设置进入下一步

![alt text](./img/13.png)

5. 名称自定义，修改磁盘位置后进入下一步

>**注意一定要修改位置，让带有该镜像的虚拟机安装除C盘外其他有充足空间的磁盘上**

![alt text](./img/14.png)

6. `指定磁盘容量`中 `最大磁盘大小` 按需进行设置，默认`拆分成多个文件`，随后进入下一步

![alt text](./img/15.png)

7. 所有配置结束，点击 `完成`

![alt text](./img/16.png)


8. 在创建的虚拟机处点击 `CD/DVD` 进行 `.iso` 文件的手动配置

![alt text](./img/17.png)

9. 启动此虚拟机
>跳出的 `侧通道缓解` 提示点击关闭即可，如果长期使用虚拟机的话建议关闭

## Ubuntu 22.04 安装流程
Ubuntu安装需要先经过DHCP网络确认，稍作等待后弹出安装界面
1. 选择 `Install Ubuntu`
>左侧系统语言默认英文，此处滚轮下滑可以选择中文，按需修改

![alt text](./img/18.png)

2. `KeyBoard Layout` 按照默认设置后 `continue`

![alt text](./img/19.png)

3. `Updates and other software` 按照默认设置后 `continue`

![alt text](./img/20.png)

4. `Installation type` 按照默认设置后 `Install Now`
>有的朋友可能看到 **Erase disk** 这个选项的关键字就害怕，但是因为我们在虚拟机下，而且之前也指定了一个安装位置，所以不会对我们的宿主机产生影响，大可放心 

![alt text](./img/21.png)

5. 随后弹出的提示依然默认 `continue`

6. 点击地图上的所在位置，这里点击板块后会默认跳到 `Shanghai`，

![alt text](./img/22.png)

7. 自定义用户名以及登录账户密码后点击 `Continue`

![alt text](./img/23.png)

8. 开始安装稍作等待，直到跳出`Restart Now` 点击即可

![alt text](./img/24.png)

9. 跳出的 `Please remove the install medium, then press Enter`， 直接回车即可

10. 欢迎来到 `Ubuntu` !

![alt text](./img/25.png)