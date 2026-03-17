>本项目仅用于个人测试使用，请部署在局域网内使用，禁止放在公网使用，禁止任何商业使用。

>本项目仅用于个人测试使用，请部署在局域网内使用，禁止放在公网使用，禁止任何商业使用。

>本项目仅用于个人测试使用，请部署在局域网内使用，禁止放在公网使用，禁止任何商业使用。
## cloud-one-system
## 简介
cloud-one-system（简称COS）—— 云端媒体库同步工具
> 本项目代码完全由 豆包、deepseek 生成，本人不懂开发，有问题也是问AI解决！

> 专为115网盘媒体整理、极速同步生成strm文件，适配Emby媒体服务器，实现媒体文件的自动整理与STRM文件同步。

> 支持天翼网盘分享订阅、夸克网盘分享订阅，可以利用桃同步上传115网盘自动整理并同步strm。

> 支持阿里网盘分享链接秒传115。

> 支持监控tg频道自动追更，实现监控频道→自动转存→自动整理→同步生成strm→刷新emby库，全自动流程。

> 本项目基于(<a class="MuiTypography-root MuiTypography-inherit MuiLink-root MuiLink-underlineAlways DDSExternalLink-root css-esgkec" rel="noopener" href="https://github.com/ChenyangGao/p115client" target="_blank">p115client<span style="white-space: nowrap; user-select: none;">&NoBreak;<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="MuiSvgIcon-root MuiSvgIcon-fontSizeInherit DDSExternalLink-icon css-1y80q5u" focusable="false" aria-hidden="true" data-testid="LinkExternalIcon"><path d="M21 9L21 3M21 3H15M21 3L13 11M10 5H7.8C6.11984 5 5.27976 5 4.63803 5.32698C4.07354 5.6146 3.6146 6.07354 3.32698 6.63803C3 7.27976 3 8.11984 3 9.8V16.2C3 17.8802 3 18.7202 3.32698 19.362C3.6146 19.9265 4.07354 20.3854 4.63803 20.673C5.27976 21 6.11984 21 7.8 21H14.2C15.8802 21 16.7202 21 17.362 20.673C17.9265 20.3854 18.3854 19.9265 18.673 19.362C19 18.7202 19 17.8802 19 16.2V14" stroke="currentColor" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path></svg></span></a>)，部分功能采用115开放平台OPEN接口。

> (<a class="MuiTypography-root MuiTypography-inherit MuiLink-root MuiLink-underlineAlways DDSExternalLink-root css-esgkec" rel="noopener" href="https://t.me/+Ch-MDMFsp1c0MDU1" target="_blank">TG反馈群<span style="white-space: nowrap; user-select: none;">&NoBreak;<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="MuiSvgIcon-root MuiSvgIcon-fontSizeInherit DDSExternalLink-icon css-1y80q5u" focusable="false" aria-hidden="true" data-testid="LinkExternalIcon"><path d="M21 9L21 3M21 3H15M21 3L13 11M10 5H7.8C6.11984 5 5.27976 5 4.63803 5.32698C4.07354 5.6146 3.6146 6.07354 3.32698 6.63803C3 7.27976 3 8.11984 3 9.8V16.2C3 17.8802 3 18.7202 3.32698 19.362C3.6146 19.9265 4.07354 20.3854 4.63803 20.673C5.27976 21 6.11984 21 7.8 21H14.2C15.8802 21 16.7202 21 17.362 20.673C17.9265 20.3854 18.3854 19.9265 18.673 19.362C19 18.7202 19 17.8802 19 16.2V14" stroke="currentColor" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path></svg></span></a>)，限量领取捐赠码！

## 主要功能
核心功能为监控115网盘指定文件夹，自动整理识别媒体文件，生成Emby、爆米花、飞牛影视、vidhub等可识别的strm文件。
## 按照步骤
1.创建cos文件夹

2.cms文件夹下创建cos.yml文件，内容如下
```
version: '3.7' 
services:
  cloud-One-System:
    privileged: true
    container_name: cloud-One-System
    image: mrfrog1989/cloud-one-system-x86:latest
    restart: always
    network_mode: bridge
    volumes:
      - "./config:/app/config"
      - "./media:/app/media"
    ports:
      - "9528:9528"
    environment: 
      PUID: 0
      PGID: 0
      UMASK: 022
      TZ: Asia/Shanghai
      COS_CODE: 捐赠码
```
3.运行 docker-compose -f cos.yml up -d ，等待部署完成

4.访问 http://127.0.0.1:9528 默认登录账号admin  默认密码admin123321
