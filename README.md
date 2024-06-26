Markdown , 文本修饰语言， 用特殊符号修饰正文效果
# Github笔记

## 一、认识Github<br>
### 1.1 Github标签<br>
Explore 探索页<br>
Topics 技术分类<br>
Trending 推送<br>
events 事件<br>

### 1.2 搜索<br>
关键字查询<br>
awesome 有趣的<br>
sample 样例<br>
tutorial 资料<br>

## 二、Github三要素<br>
### 2.1 仓库<br>
仓库是Github的项目管理单元，每个用户都可以创建属于自己的仓库将项目代码资源上传到仓库中保存。项目传到github中可以云存储 保存与备份。便于管理工程，每个仓库中存储一个工程。每个用户都可以有多个仓库<br>
便于分享，可以通过https连接分享仓库数据。<br>
### 2.2 提交<br>
用户在上传代码时，可以用过提交来备份代码信息。<br>
提交可以备份代码片段，并且统计展示用户的修改。通过提交记录找到以前的代码片段（良好的提交习惯）。<br>
可以通过提交记录，回溯任意代码位置。提交可以记录开发的详细过程（文件的创建，即代码的修改）便于用户学习工程的开发过程。<br>
### 2.3 分支
资源存储单位，用于存储代码数据，一个仓库由若干分支构成。<br>
每个仓库创建后都有一个默认主分支（Matser/Main），代码上传都存储在分支里。可以用于多人协作开发。<br>

## 三、Git的配置与使用
`Git 分布式版本控制系统`<br>
Github网站仓库中的工程、已上线发布的工程，开发者可以随时使用git软件，对项目进行更新、访问、控制与管理，用于同步管理线上工程<br>
![本地设备与云端仓库的交互逻辑](https://github.com/Bigdata-shiyang/ceshi/blob/master/202406091907023.png "本地设备与云端仓库的交互逻辑")


### 3.1 绑定远程仓库
1. 完成账号与设备绑定<br>
   1. 查看本地配置文件<br>
   ```bash
   git config --list
   ```
   2. 修改或添加config配置项<br>
   ```bash
   git config --global user.name 用户名
   git config --global user.email 注册邮箱
   ```
   3. 生成本机设备密文<br>
   ```bash
   ssh -keygen -t rsa -C 注册邮箱
   ```
   4. 测试关联是否完成<br>
   ```bash
   ssh -T git@github.com
   ```
2. 为目标仓库设置别名，创建一个云端仓库的SSH地址别名<br>
   ```bash
   git remote add orgin(别名) SSH地址(云端仓库地址)

   git remote origin remove #删除地址别名
   ```

### 3.2 本地资源上传<br>
1. 创建本地仓库<br>
```bash
git init
```
2. 将数据添加到缓冲区<br>
```bash
git add 文件名 #将数据资源添加到git缓冲区

git status #查看git缓冲区
```
3. 将缓冲区数据提交到本地仓库
```bash
git commit #提交到本地仓库

git commit -m "备注信息" #生成提交记录
```
4. 将本地仓库内容推到云端仓库
```bash
git push origin master
#将本地分支上传到云端，如果分支重名则合并，否则云端创建新的分支保存上传内容
```

### 3.3 删除<br>
1. 还原/删除本地文件
```bash
git restore 文件名 #将本地删除的文件还原（本地仓库中有备份）
```

```bash
git rm 文件名 #删除本地仓库的同时删除本地文件，无法还原
```

2. 上传删除操作，删除云端
```bash
git commit -m "删除操作"

git push origin master
```

### 3.4 获取云端数据<br>
1. 下载源码
```bash
git clone https 项目地址
```
2. 拉取仓库
```bash
git pull
```
如果此时直接上传会显示失败<br>


`要通过git提交，不可以在云端直接修改`<br>
如果在云端进行修改，此时云端比本地新，依赖关系被改变，本地无法再进行上传<br>
此时可以先拉取更新云端，再推送本地资源<br>
```bash
git pull --rebase origin master

git rebase --abort #忽略新版，此时还不能上传
git rebase --skip #忽略旧版，更新本地后可以上传
git rebase --continue #版本合并，解决冲突后可以直接上传
```

## 四、Maekdown(文本修饰语言)

## 标题修饰符\#

# 标题修饰符（一级标题）
## （二级标题）
### （三级标题）
#### （四级标题）
##### （五级标题）

## 正文内容
  输入正文内容，如果需要换行，用 \<br\> 标签

## 修饰正文

*一段测试代码*

**一段测试代码**

***一段测试代码***

~~一段测试代码~~

将`关键字`,重点表明

## 分割线
  用 \-\-\- 表示分割线
---

## 引用效用\>表示
> 你自己就是一座金矿
>> 苏格拉底
>>> 三级引用
>>>> 四级引用

## 列表修饰符
### 无序列表 \*
* 二次元游戏
  * 原神
    * 神力
* 大逃杀类
  * PUBG
    * APEX

### 有序列表 1.
1. 物理学
   1. 粒子物理
   2. 原子核物理
   3. 凝聚态物理
2. 计算机
   1. 分布式架构
   2. 云计算
### 混合列表
1. 测试一级
  * 测试二级
    2. 测试三级

### 表格
名称|技能|排行
--|:--:|--:
蝙蝠侠|富有|1
蜘蛛侠|吐丝|2
钢铁侠|富有|3

### 代码片段
```c
	#include<stdio.h>
```
```cpp
	#include<iostream>
```
```bash
	echo "测试"
```

### 超链接技术

[Github](https://www.github.com "点击访问")

### 插入图片
![代码截图](https://github.com/Bigdata-shiyang/ceshi/blob/master/202406091859359.png "代码长截图")

