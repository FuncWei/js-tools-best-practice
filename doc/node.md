# nodejs

## nvm 快速切换 Node 版本

nvm: https://github.com/creationix/nvm

nvm 默认是从 http://nodejs.org/dist/ 下载的, 国外服务器, 必然很慢,
好在 nvm 以及支持从镜像服务器下载包, 于是我们可以方便地从七牛的 node dist 镜像下载:

```
$ NVM_NODEJS_ORG_MIRROR=https://npm.taobao.org/dist nvm install 0.11.11
```

于是你就会看到一段非常快速进度条:

```
######################################################################## 100.0%
Now using node v0.11.11
```

如果你不想每次都输入环境变量 NVM_NODEJS_ORG_MIRROR, 那么我建议你加入到 .bashrc 文件中:

### nvm

```
export NVM_NODEJS_ORG_MIRROR=https://npm.taobao.org/dist
source ~/git/nvm/nvm.sh
```
然后你可以继续非常方便地安装各个版本的 node 了, 你可以查看一下你当前已经安装的版本:

```
$ nvm ls
         nvm
     v0.8.26
    v0.10.26
    v0.11.11
->  v0.11.12
```

## nrm 快速切换 NPM 源

http://www.tuicool.com/articles/nYjqeu

### 安装

	$ npm install -g nrm

### 使用

列出可选的源

	nrm ls                                                                                                                                    

	* npm ---- https://registry.npmjs.org/
	cnpm --- http://r.cnpmjs.org/
	taobao - http://registry.npm.taobao.org/
	eu ----- http://registry.npmjs.eu/
	au ----- http://registry.npmjs.org.au/
	sl ----- http://npm.strongloop.com/
	nj ----- https://registry.nodejitsu.com/

带` * `的是当前使用的源，上面的输出表明当前源是官方源。

### 切换

切换到taobao

	nrm use taobao                                                                                                 Registry has been set to: http://registry.npm.taobao.org/

增加源

你可以增加定制的源，特别适用于添加企业内部的私有源。 私有源可以使用cnpmjs架设 。

	nrm add  <registry> <url> [home]

删除源

	nrm del <registry>

测试速度

你还可以通过 nrm test 测试相应源的响应时间。

例如，测试官方源的响应时间：

	nrm test npm                                                                                                                               

  	npm ---- 1328ms

测试所有源的响应时间：

	nrm test                                                                                                                                   
	npm ---- 891ms
	cnpm --- 1213ms
	* taobao - 460ms
	eu ----- 3859ms
	au ----- 1073ms
	sl ----- 4150ms
	nj ----- 8008ms

注意，为了取得较准确的结果，可以考虑多次测试取平均值。

许可

nrm 为开源软件，使用 MIT 许可。

项目主页

github.com/Pana/nrm

## 发布npm

直接的npm init还是要做的，待要发布的时候增加用户，然后publish

	npm adduser
	npm publish --tag 0.1.0  


最后，如果你报错

	no_perms Private mode enable, only admin can publish this module

那么可能是你用了国内的镜像地址了，只需要重新把地址注册回npmjs即可。

	npm config set registry http://registry.npmjs.org
	
or

	nrm use npm


## npm推荐

### node-open

使用mac打开文件夹的时候竟然使用open命令，比如

- 打开文件夹
- 打开浏览器

node里有open这个模块，并且适配各平台的open，有兴趣的可以自己去看一下源码

https://github.com/pwnall/node-open



