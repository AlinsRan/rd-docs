
# notice

## 基础环境安装

* [Golang](https://go.dev/doc/install)
* [Docker](https://docs.docker.com/engine/install/ubuntu/)
* [Kind](https://kind.sigs.k8s.io/)
* [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)
* [Helm](https://helm.sh/docs/intro/install/#from-the-binary-releases)

## Golang

* env

```shell
#使用国内镜像，避免无法访问
go env -w GOPROXY=https://goproxy.cn,direct
#自动跟踪软件包版本
go env -w GO111MODULE=on
```

## Docker

* 定于`sudo service docker start` 启动daemon报错：`wsl ubuntu22.04 iptables filed` 解决方法.

`sudo update-alternatives --set iptables /usr/sbin/iptables-legacy` or set `net.ipv4.ip_forward = 1` in `/etc/sysctl.conf`

* [非root权限问题](https://www.digitalocean.com/community/questions/how-to-fix-docker-got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket)

```shell
sudo gpasswd -a $USER docker #将登陆用户加入到docker用户组中
newgrp docker #更新用户组
```

### 镜像加速

* 编辑 `/etc/docker/daemon.json` 配置
* 使用国内镜像加速访问 dockerhub 仓库

```json
{
    "registry-mirrors": ["https://registry.docker-cn.com","https://hub.daocloud.io","https://docker.mirrors.ustc.edu.cn"]
}
```

* 通过`/var/log/docker.log`查看docker日志

### Desktop

* [wsl2 disk question](https://stackoverflow.com/questions/62441307/how-can-i-change-the-location-of-docker-images-when-using-docker-desktop-on-wsl2)
 
## Git

* 基本配置

```shell
#使用国内镜像加速访问github
git config --global url."https://hub.fastgit.xyz/".insteadOf https://github.com/

#配置个人信息
git config --global user.name "${name}"
git config --global user.email "${email}"

#github添加密钥并使用ssh方式提交
#生成密钥，一路回车,把密钥放到github上
ssh-keygen -o
cat ~/.ssh/id_rsa.pub
#测试能否连上
ssh -T git@github.com
```

* 同步主仓库

```shell
#个人fork仓库同步主仓库
git remote add upstream ${https://github.com??? 主仓库}
git fetch upstream
git merge upstream/master
git push origin master
```

* 基本使用

```shell
#拉取仓库
git clone ${ssh 项目}
#查看更改
git status
#提交更改
git add ${更改的文件或目录}
git commit -m "${你的commit消息}"

#更新本地仓库并推送
git pull
git push origin

#强制提交
git push -f origin

* 常用命令

```shell
#查看commit记录
git log

#撤销某个commit的更改
git revert ${commit_id}

#查看历史更改信息
git reflog

#回退到某个历史版本
git reset --mixed ${id}

#合入某个版本
git cherry-pick ${commit_id}

#查看分支
git branch

#创建分支
git branch ${分支名}

#切换分支
git checkout ${分支名} 

#拉取远程分支，创建并切换到本地分支
git checkout -b ${分支名} origin/${分支名}
```

## WSL

### 快照迁移

```cmd
#导出系统包到指定目录
wsl --export Debian "D:\WSL\Debian\data.tar"

#注销子系统
wsl --unregister Debian

##导入系统包 指定卷位置 目标系统包
wsl --import Debian "D:\WSL\Debian" "D:\WSL\Debian\data.tar"
```

### 压缩磁盘空间
 
> wsl 下vm不会自动缩容，docker堆积的内存，占用的磁盘空间. 需要主动释放。运行以下命令需要管理员权限。
```cmd
diskpart

select vdisk file="C:\Users\13242\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu20.04LTS_79rhkp1fndgsc\LocalState\ext4.vhdx"

attach vdisk readonly
compact vdisk
detach vdisk

exit
```

## Ginkgo
- 聚焦或跳过spec
  - --skipMeasurements
如果设置该参数，Ginkgo 会跳过任何你定义的 Measure spec 。
  - --focus=REGEXP
如果设置该参数，Ginkgo 只会运行带有符合正则表达式 REGEXP 的描述的 spec。
  - --skip=REGEXP
如果设置该参数，Ginkgo 只会运行不有符合正则表达式 REGEXP 的描述的 spec。
