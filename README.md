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

##　for labplus

项目以repo方式管理，wwww.github.com/labplus-cn/创建canmv_k230_manifest仓库管理项目repo.

需要二次开发的仓库：canmv_k230 和 lvgl

从https://github.com/kendryte/canmv_k230.git fork 到www.github.com/labplus-cn做二次开发。

lvgl fork到wwww.github.com/labplus-cn，按需配置并加入字体。

两个仓库可单独通git操作创建分支、推送等操作。

项目拉取：

1. 参照BUILD.md，创建开发环境及编译。
2. 拉取项目到本地（项目仓库以repo方式管理）
   mkdir -p canmv_k230
   cd canmv_k230
   repo init -u https://github.com/labplus-cn/canmv_k230_manifest -b master --repo-url=https://github.com/canmv-k230/git-repo.git
   repo sync 

    注意，第一次repo sync拉取的是manifest里定义的各仓库的默认分支，且处理游离状态，需要对二次开发的仓库创建并切换到新的分支
   git checkout -b labplus dev/labplus_canmv