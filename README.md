<img height=230 src="https://github.com/kendryte/k230_canmv/blob/main/images/CanMV_logo_800x260.png">

**CanMV, 让 AIOT 更简单～**

CanMV 的目的是让 AIOT 编程更简单， 基于 [Micropython](http://www.micropython.org) 语法, 运行在[Canaan](https://www.canaan-creative.com/)强大的嵌入式AI SOC系列上。目前它在K230上运行。

## 镜像下载

1. **[PreRelease](https://github.com/kendryte/canmv_k230/releases/tag/PreRelease)**: 开发分支自动编译生成镜像，供测试使用，尽保留最新版本

2. 预编译release镜像：请访问[嘉楠开发者社区](https://developer.canaan-creative.com/resource), 然后在`K230/Images`分类中，下载镜像文件名包含`micropython`的文件，并烧录至SD卡中。(镜像文件名格式：`*_micropython_*.img.gz`)

> 下载的镜像默认为`.gz`压缩格式，需先解压缩，然后再烧录。

> micropython镜像与K230 SDK镜像所支持的功能并不相同，请勿下载K230 SDK镜像来使用micropython

## 快速开始

### 自行编译镜像

参考[BUILD](BUILD.md)，可使用`Dokcer`或本地环境编译，编译速度更快

或者参考[K230 CanMV 自定义固件](https://developer.canaan-creative.com/k230_canmv/main/zh/userguide/how_to_build.html)

### 烧录

linux下直接使用dd命令进行烧录，windows下使用烧录工具进行烧录，可参考[K230 CanMV 如何烧录固件](https://developer.canaan-creative.com/k230_canmv/main/zh/userguide/how_to_burn_firmware.html)

## 贡献指南

如果您对本项目感兴趣，想要反馈问题或提交代码，请参考[CONTRIBUTING](CONTRIBUTING.md)

## 联系我们

北京嘉楠捷思信息技术有限公司

网址:[www.canaan-creative.com](https://www.canaan-creative.com/)

商务垂询:[salesAI@canaan-creative.com](salesAI@canaan-creative.com)

## for labplus

二次开发需要修改一些仓库，从官网fork以下仓库到公司官网：

https://github.com/labplus-cn/canmv_k230.git

https://github.com/labplus-cn/canmv.git

https://github.com/labplus-cn/lvgl.git

项目拉取：

1. 参照BUILD.md，创建开发环境及编译。
2. 从官方拉取项目到本地（项目仓库以repo方式管理）

   ```bash
   mkdir -p canmv_k230
   cd canmv_k230
   repo init -u https://github.com/canmv-k230/manifest -b master --repo-url=https://github.com/canmv-k230/git-repo.git
   repo sync 
   repo star labplus_canmv --all # 本地创建分支做二次开发
   ```
3. 二次开发仓库添加公司远程
   
   ```bash
   # 拉取本地canmv_k230仓库
   cd canmv_k230
   git remote add labplus https://github.com/labplus-cn/canmv_k230.git
   git pull labplus labplus_canmv # 从公司仓库拉取本仓库开发分支
   git checkout labplus_canmv

   # 拉取本地canmv仓库
   cd canmv_k230/src/canmv
   git remote add labplus https://github.com/labplus-cn/canmv.git
   git pull labplus labplus_canmv 
   git checkout labplus_canmv

   # 拉取本地lvgl仓库
   cd ccanmv_k230/src/canmv/port/3rd-party/lv_bindings/lvgl
   git remote add labplus https://github.com/labplus-cn/lvgl.git
   git pull labplus labplus_canmv 
   git checkout labplus_canmv
   ```
   说明：第一次repo sync拉取的是manifest里定义的各仓库的默认分支，且处于游离状态，需要执行上述操作拉取二次开发的仓库并切换到新的分支。
   
   也可以对某一仓库创建新分支开发。跟单独仓库的git操作一样。但repo项目时，一定要切换到开发仓库。
