# npm
#### 什么是npm？
**npm(node package manager)node包管理器**
```
1. npm -V 查看版本号
2. bodyparser express
3. http url fs
```
#### npm管理包的哪些方面？
> 下载

```
1.本地下载
（1）-D  安装本地开发依赖 ---->devDependencies字段内
（2）-S  安装本地线上依赖 ---->dependencies字段内

2.全局下载
  生成package.json    包描述文件
（1）npm init
（2）npm init -y      快速生成
```

> 更新

```
 npm undate <包名> -D/-S
```
> 卸载

```
1.本地卸载
  npm uninstall   <包名>-P/-S

2.全局卸载
  npm unistall
```

---

# nodejs
==nodejs ---->commomjs规范==

==一个js就是一个模块==

#### commonjs 规范
1.抛出模块
```
module.exports   后者会覆盖前者

exports
```

*module.exports和exports的区别和关系：*
```
exports是module.exports的别名
```
2.引入模块：
```
require()
默认它会找module.exports抛出的内容
```

---
# npm包查找规则
require（模块标识）

#### 模块标识：

**1.路径（相对路径和绝对路径**）


```
（1）./

（2）/
```


**2.包名**


```
（1）现在当前文件夹下找 ----> 一层一层向上找知道找到磁盘根目录
     全局配置环境变量NODE_PATH查找
     
     -报错-Error:Cannot find module ‘包名’
     
     
（2）先找对应包名文件夹：package.json main字段 没有index.js
     -报错-：不是内部外部命令，把执行文件放在全局环境的path下。
     
     npm root -g 是查看全局下载包的路径
```


---

# git生成公钥h和秘钥

**GitHub生成两种协议：**


```
1.https

2.ssh
```
**https：每次提交代码，都需要输入用户名和密码**

**ssh：需要配置公钥和秘钥**

**ssh-keygen———生成公钥、秘钥指令**

---

# 设置镜像源

***国外*：http：//registry.npmjs.org/**

***淘宝*：https：//registry.npm.taobao.org**

**设置镜像源地址：npm config set registry  <镜像源地址>**   

**查看镜像源地址：npm config get registry**

---

# 下载包步骤
**1.对应的镜像源查看是否存在执行包**

**2.把指定的压缩包下载到指定的缓存目录下**

```
查看指令：npm config get cache
```

**3.把压缩包解压到指定目录**
```
设置全局的解压目录：npm config set prefix <绝对路径>
```

---

# npm常用的命令


```
npm view <包名> versions -----所有的版本

npm view <包名> version -----最新的版本

npm search <包名>  -----发布npm包，验证包是否存在

npm config get prefix -----查看全局的解压目录
```

---

# 发包

1. **npm 镜像源必须是国外的**
2. **必须要有包描述文件package.json文件     ----->==name一定不能和现有的name重复==**
3. **新建入口文件 编写功能**
4. **npm login**
5. **npm publish**
6. **npm unpublish <包名> -- force** ---->在24小时内发的包可以删除

