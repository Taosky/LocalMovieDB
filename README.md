# LocalMovieDB
基于豆瓣信息的（简易）本地电影数据库（Web），用于NAS电影检索。(<del>由于原来流传豆瓣API key权限没收,可能无法使用</del>)。
新的分支已解决该问题，并提供了API（详见`douban.py`）


## 功能
- 获取本地电影豆瓣信息（可定时运行）
- 推送新电影消息至Telegram和Bark
- Web页面展示电影列表和播放页面（调用PC、移动端视频软件）
- 标题搜索、排序、Tag筛选

![PC0](https://raw.githubusercontent.com/Rocket-Factory/LocalMovieDB/legolas/preview/PC0.png)
![MB0](https://raw.githubusercontent.com/Rocket-Factory/LocalMovieDB/legolas/preview/PC1.png)
![MB1](https://raw.githubusercontent.com/Rocket-Factory/LocalMovieDB/legolas/preview/mb0.png)
![MB1](https://raw.githubusercontent.com/Rocket-Factory/LocalMovieDB/legolas/preview/mb1.png)


## 使用
1. 创建Python3虚拟环境，安装依赖。
2. 创建配置文件`config.py`，注意命名正则。
3. 运行`app.py`，手动执行`job.py`获取电影信息。
4. 创建cron任务，定时执行`job.py`更新电影信息。

## 注意
1. 电影路径格式要求：默认（可自行设置正则）为`豆瓣电影名（年份）`，路径内需存在视频文件。
2. 评论功能需要手动输入消息链接，需要科学上网查看。
3. 豆瓣API会去获取新的电影和剧集，如不存在可能会导致数据库收录和推送失败，建议先打开`https://douban.8610000.xyz/data/<豆瓣Subject ID>.json`查看是否存在（<del>不存在会自动加入服务器队列，半个小时后再查看应该就有了</del>）。
4. <del>服务器资源十分有限，仅方便个人整理和分享，请勿滥用。</del>已通过存放在Github解决。

## 更新

### 2021-01-17
1. 切换API到Github Pages，避免服务器流量问题

### 2021-01-03
1. 修复bug，优化细节
2. 支持IOS PWA（Safari 添加到主屏幕）
3. 详情页返回不再重载首页
4. 新增IINA播放

### 2020-12-28
- `legolas`分支重写了Web页面
- 适配Potplayer和VLC（移动端）
- 合并推送功能（TansmissionNotify不再更新）
- 新增绑定Telegram消息评论功能（需公开群组或频道）
- 修复BUG

### 2020-11-10
- 修复API问题
- 新增视频app快捷播放页面
- 新增简介
