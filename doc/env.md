
# notice

## VM

### 压缩磁盘空间

*** 
wsl 下vm不会自动缩容，docker堆积的内存，占用的磁盘空间  

windows cmd命令:
```cmd
diskpart

select vdisk file="C:\Users\13242\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu20.04LTS_79rhkp1fndgsc\LocalState\ext4.vhdx"

attach vdisk readonly
compact vdisk
detach vdisk

exit
```

## docker

* wsl ubuntu22.04tls iptables filed

`sudo update-alternatives --set iptables /usr/sbin/iptables-legacy`

## Git
> 使用镜像加速github.com的访问  
> git config --global url."https://hub.fastgit.xyz/".insteadOf https://github.com/  
>
基本使用
```shell
#配置
git config --global user.name "rongxin"
git config --global user.email "rongxin@api7.ai"

#同步个人库
git remote add upstream https://github.com???
git fetch upstream
git merge upstream/master

#push库
git push origin 
```

## Ginkgo
- 聚焦或跳过spec
  - --skipMeasurements
如果设置该参数，Ginkgo 会跳过任何你定义的 Measure spec 。
  - --focus=REGEXP
如果设置该参数，Ginkgo 只会运行带有符合正则表达式 REGEXP 的描述的 spec。
  - --skip=REGEXP
如果设置该参数，Ginkgo 只会运行不有符合正则表达式 REGEXP 的描述的 spec。
