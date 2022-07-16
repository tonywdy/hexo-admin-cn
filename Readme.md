![logo](docs/logo.png?raw=true)

[Hexo博客引擎]的管理UI(http://hexo.io). 基于[幽灵](http://ghost.org)界面，灵感来自[svbtle](http://svbtle.com)和[散文](http://prose.io).

## Hexo版本

2022.7.16 目前支持最新版HEXO，本汉化将实时同步hexo-admin

### 目录
- [**屏幕截图**](#屏幕截图)
- [**快速启动**](#快速启动)
- [**信用**](#信用)

# 本地使用与部署
这个插件最初设计为一个本地编辑器——在本地运行```hexo```，使用```hexo admin cn```创作帖子，然后使用```hexo generate```或```hexo deploy```生成的静态```HTML```文件发送到```github```页面或其他静态服务器。

不过，只要你使用非静态托管服务，如```Heroku```、```DigitalOcean```等，就可以在你的```live```博客上运行```hexo admin```。静态托管服务，如```Github pages```和```Surge.sh```不支持从您的```live```站点运行```hexo admin cn```。

如果你在live博客中使用Hexo admin，你一定要设置密码（见下文）——否则任何人都可以编辑你的内容。

# 屏幕截图
![posts view](https://s2.loli.net/2022/07/16/aZXtbLTNiBUqSjh.png)

![editor view](https://gitlab.com/KINGWDY/photobed/-/raw/main/pictures/2022/07/16_16_11_7_20220716161105.png)

# 快速启动
### 1、设置hexo并创建博客
```sh
npm install -g hexo
cd ~/
hexo init my-blog
cd my-blog
npm install
```
### 2.安装hexo-admin-zhcn并启动
```sh
npm install --save hexo-admin-zhcn
hexo server -d
open http://localhost:4000/admin/
```
### 3、利润！
用户界面应该很容易发现——如果你找不到什么，请告诉我。

### 4、密码保护
如果你在live server上使用Hexo admin，你需要一些密码
保护为了实现这一点，只需在hexo中添加几个配置变量
`_config.yml`:

```
admin:
  username: myfavoritename
  password_hash: be121740bf988b2225a313fa1f107ca1
  secret: a secret something
```

![](https://gitlab.com/KINGWDY/photobed/-/raw/main/pictures/2022/07/16_16_14_11_20220716161411.png)

“password\hash”是密码的bcrypt哈希。使用```秘密```
为了保证饼干的安全，最好把饼干放长一点(复杂的)

Hexo admin设置中的实用程序可以散列您的密码并生成```admin```
为您准备的部分。启动Hexo，进入“设置>设置身份验证”`
并填写您的信息。将生成的YAML复制到您的```_config.yml`。

一旦这一切就绪，启动hexo服务器并转到```/admin/```将要要求您输入密码。

### 5、自定义post元数据
要使用管理界面添加和编辑您自己的帖子元数据，请添加
元数据变量和自定义变量`_config.yml`:
```
metadata:
  author_id: defaultAuthorId
  language:
```
![](https://gitlab.com/KINGWDY/photobed/-/raw/main/pictures/2022/07/16_16_16_23_20220716161623.png)

您可以提供用于初始化元数据的默认值
一个新职位。这些可以是基元或数组。

### 6、贡献！
- 让我知道如何进行改进
  [githubissues](https://github.com/jaredly/hexo-admin-zhcn/issues)
- [fork](https://github.com/tonywdy/hexo-admin-zhcn) 和拉请求

# 信用

本插件为KINGWDY汉化！具体事项请看[我的博客](https://tonywdy.github.io/)！

![](https://avatars.githubusercontent.com/u/106950730?s=96&v=4)

