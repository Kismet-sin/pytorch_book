# 用Gitbook组织文档并展示到Github的Pages中

> *Gitbook* 是一个基于 *Node.js* 的命令行工具，可使用 *Github/Git* 和 *Markdown* 来编写电子书。支持 *Markdown*，插件众多是其最大特点，用来组织产品文档，FAQ或WIKI都是不错的选择。
> 
> *Github* 的 *Pages* 功能则允许将创建好的电子书文档发布到个人网页，以便于在线访问。

## 第一阶段：安装Gitbook实现本地预览

> 此阶段的目的为在本地安装 *Gitbook* ，并成功的预览文件

**1)** 为了可以在 *Windows10* 本地编译和预览 *Gitbook* 生成的文档，需要先下载 *nodejs* 并安装

下载地址：[https://nodejs.org/en/](https://nodejs.org/en/)，推荐下载稳定版

![image](https://ws1.sinaimg.cn/large/007DaZrGgy1g2h9rem3g8j30qp0eq75m.jpg)

安装过程不表，默认安装即可

**2)** 安装完成后，需要将安装路径添加到「环境变量」中，以便于在命令行中使用node和npm相关命令，
```
注释：配置路径为：控制面板->系统和安全->系统->高级系统设置->环境变量（按钮）
```
![image](https://ws2.sinaimg.cn/large/007DaZrGgy1g2hazwb1wbj30kd0iz77r.jpg)

**3)** 配置完成后，在命令行中键入```node -v```或```npm -v```，若如图显示出对应版本号，则说明安装和配置都已完成

![image](https://wx3.sinaimg.cn/large/007DaZrGgy1g2haqx28qej30el040jrf.jpg)

**4)** 下一步，在命令行中键入```npm install gitbook-cli -g```，开始安装gitbook

![image](https://ws3.sinaimg.cn/large/007DaZrGgy1g2hbghc36sj30md03174n.jpg)

**5)** 在 [Github](github.com) 上新建一个仓库 *Repository* （当然你首先得有Github账号），命名为 *Test* 。选择项目类型为公开 Public，并且
勾选 *Initialize this repository with a README* 以便创建README文件(建议勾选，似乎是gitbook本地编译时必须的文件)

![image](https://wx3.sinaimg.cn/large/007DaZrGgy1g2hbrnr2dnj30np0h275r.jpg)

创建好以后把远程仓库克隆到本地，切换到 *Test* 目录下，可以看看初始目录有哪些文件

![image](https://ws1.sinaimg.cn/large/007DaZrGgy1g2hc3ixle5j30il08r0un.jpg)

**6)** 命令行中键入```gitbook init```初始化项目，初次操作会显示 *Installing GitBook 3.2.3* ，需要等待一些时间让他自动安装一些插件，完成后会提示 *info: initialization is finished* ，Gitbook 自动创建了 *SUMMARY.md* 文件，这是电子书的目录文件

![image](https://wx1.sinaimg.cn/large/007DaZrGly1g2hcn29k9cj30g80drdj4.jpg)

**7)** 命令行中键入```gitbook serve```会启动一个本地的服务（同时会新增一个 *_book* 目录），在浏览器其中访问地址就可以实时预览电子书

![image](https://ws1.sinaimg.cn/large/007DaZrGly1g2hcrurbs3j30ga094wg6.jpg)

^_^ 预览成功！！！

![image](https://wx2.sinaimg.cn/large/007DaZrGly1g2hctjqpd3j30ma0bst9d.jpg)

## 第二阶段：展示到Github的page中

> 这个阶段的最终目的是要将我们本地编辑的文档通过 *Github* 的 *Pages* 功能实现在线访问

**1)** 在 *Test* 的项目里点击 *settings* ，找到 *GitHub Pages*

![image](https://wx4.sinaimg.cn/large/007DaZrGgy1g2hdegsaubj30ui030t8u.jpg)

*Source* 我选择用 *docs* 目录下的内容来呈现项目文档，但这时发现选项是「禁用」的！！！

![image](https://wx3.sinaimg.cn/large/007DaZrGly1g2hdbiwnk4j30mv0avt9f.jpg)

**2)** 在本地环境中先将编译文档到 *docs* 目录（这里我新增了一个 *Blog.md* 文件） ，在 *SUMMARY.md* 中添加访问链接后可直接在左侧的目录树显示

命令行中键入```gitbook build . docs```，将文件都编译到 *docs* 目录下

![image](https://wx3.sinaimg.cn/large/007DaZrGgy1g2hk9q22qoj30hj0an76u.jpg)

**3)** 然后将编译好的文件 *PUSH* 到远端仓库

```
$ git add *
$ git commit -m"Inital commit"
$ git push orgin master
```

**4)** 此时，再去 *Settings* 里去设置 *Pages* 的 *Source* ,发现 *master branch/docs folder* 已经是可选的，选择后页面会刷新生成访问地址

![image](https://ws3.sinaimg.cn/large/007DaZrGgy1g2hkkwy1ouj30ls0axdgk.jpg)

^_^ 恭喜，能走到这一步，证明我们已经成功的将文档发布到 *Github* 的 *Pages* ，我们只需要访问地址即可:

![image](https://wx2.sinaimg.cn/large/007DaZrGgy1g2hkp2d9qbj31490ldwis.jpg)

终于写完了，好TM累，睡觉。。