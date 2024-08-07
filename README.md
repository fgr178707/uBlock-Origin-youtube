### youtube广告拦截

uBlock Origin下载地址
* [Microsoft Edge](https://microsoftedge.microsoft.com/addons/detail/ublock-origin/odfafepnkmbhccpbejgmiehpchacaeak)
* [google Chrome](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm)
* [Firefox](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/)
* [Opera](https://addons.opera.com/en/extensions/details/ublock/)
* [手动安装](https://github.com/gorhill/uBlock/releases)


### 动态规则
* 设置方法
    1. uBlock Origin->设置->勾选我是高级用户
    2. 设置->自定义动态规则->临时规则->保存->提交

```
no-csp-reports: * true
no-large-media: behind-the-scene false
behind-the-scene * * noop
behind-the-scene * 1p-script noop
behind-the-scene * 3p noop
behind-the-scene * 3p-frame noop
behind-the-scene * 3p-script noop
behind-the-scene * image noop
behind-the-scene * inline-script noop
www.youtube.com * 3p block
www.youtube.com * 3p-frame block
www.youtube.com * 3p-script block
www.youtube.com fonts.googleapis.com * noop
www.youtube.com fonts.gstatic.com * noop
www.youtube.com googlevideo.com * noop
www.youtube.com i.ytimg.com * noop
www.youtube.com photos-ugc.l.googleusercontent.com * noop
www.youtube.com www.gstatic.com * noop
www.youtube.com youtube-ui.l.google.com * noop
www.youtube.com yt3.ggpht.com * noop
www.youtube.com yt3.googleusercontent.com * noop
```



### 静态规则
***优先选择动态规则***
* 设置方法
    1. 自定义静态规则->粘贴到下面输入栏->应用更改


```
! 2024-07-23 https://www.youtube.com
youtube.com##+js(set, yt.config_.openPopupConfig.supportedPopups.adBlockMessageViewModel, false)
youtube.com##+js(set, Object.prototype.adBlocksFound, 0)
youtube.com##+js(set, ytplayer.config.args.raw_player_response.adPlacements, [])
youtube.com##+js(set, Object.prototype.hasAllowedInstreamAd, true)
```

### 正处于测试阶段的动态规则
**如发现问题随时反馈给我[反馈](https://github.com/fgr178707/uBlock-Origin-youtube/issues/new)**
```
no-remote-fonts: www.youtube.com false
no-large-media: www.youtube.com false
www.youtube.com * 1p-script noop
www.youtube.com * inline-script noop
www.youtube.com google.ch * noop
www.youtube.com google.com * noop
www.youtube.com google.de * noop
no-remote-fonts: www.youtube.com true
no-popups: www.youtube.com true
```

