---
title: hexo搭建博客并同步
date: 2018-07-28 16:20:04
tags: 安装与使用
---
## 搭建博客
在任意盘下创建文件：
```
mkdir hexo
cd hexo
hexo init
```
修改_config.yml如下：
```
deploy:
  type: git
  repo: https://github.com/feifei1993/feifei1993.github.io.git
  branch: master
```
安装：
```
npm install hexo-deployer-git --save
```
生成并测试：
```
hexo g
hexo s
```
在浏览器中输入`http://localhost:4000/`查看结果
上传到github：
```
hexo d
```
稍等片刻后，在浏览器中输入`feifei1993.github.io`查看结果

## 多电脑同步
新建分支hexo，并设置为默认分支
克隆到本地：
```
git clone https://github.com/feifei1993/feifei1993.github.io.git
```
将`hexo`目录下文件拷贝到`feifei1993.github.io`
执行：
```
git add .
git commit -m 'emm'
git push
```
## 新电脑
克隆到本地：
```
git clone https://github.com/feifei1993/feifei1993.github.io.git
npm install
```
修改配置或者博客后
执行：
```
git add .
git commit -m 'emm'
git push
hexo clean
hexo d -g
```
注意每次更换电脑都要进行`git pull`

