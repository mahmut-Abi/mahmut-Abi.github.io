---
title: 有雀可视化部署
date: 2022-12-16 18:07:00 +/-TTTT
categories: [TOP_CATEGORIE, SUB_CATEGORIE]
tags: [test-tag]     # TAG names should always be lowercase
---

# 有雀可视化部署

## 需求

1. 可视化，自动化部署有雀集群。
2. 集群安装后的的伸缩等操作。
3. 需支持有燕+有岳
4. 裸机+OpenStack

### 实现方式

* 修改官方ansible脚本

* 修改sealer
* 开发部署工具

### 实现流程：

1. 系统安装（有燕+有岳）（PXE）
2. 基础节点初始化（根据用户输入生成配置）。
3. 初始化引导节点。
4. 初始化master节点。
5. 加入worker节点。

#### 有燕有岳部署区别：

* 有燕可以使用uccps镜像，有岳需要装包。

* 有燕在安装系统时传入ignition，启动即生效。有岳需安装完包，再传入ignition重启生效。



## 自动化部署

### openshift ansible 部署

* https://github.com/openshift/openshift-ansible

​	简介：



优点：

1. 官方提供工具，减少工作量。
2. 脚本易于修改，便于调试。
3. 方便的添加新功能。

缺点：

1. 已不支持openshift 4.x 的版本。
2. 

### openshift-installer

优点：

1. 支持PXE安装
2. 官方支持，一直在更新







## 可视化方式

* GUI (Graphical User Interface)
* WEB
* TUI (Text-based User Interface)

注：无论何种可视化工具，均需与所部属的集群网段互联。因此，不管是CS/BS 架构都需在集群网段部署。

### GUI

优点:

1. 面向普通桌面用户
2. 界面可以更好看

缺点：

1. 可能需要以安装包形式提供安装，依赖图形化桌面，不支持最小化安装的系统。
2. 更新迭代可能需要用户升级。

### WEB

优点：

1. 不需要安装客户端软件。
2. 服务端更新迭代方便(可以提供容器)。

缺点:

1. 不适合最小化安装系统运行。
2. 开发周期可能较长。

### TUI

优点：

1. 适应大部分Linux端，不需依赖图形化界面。
2. 可以CS合一。

缺点：

1. 可能界面不是很美观。
2. 操作可能对新手不是很友好。
