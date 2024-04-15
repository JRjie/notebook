---
title: Command_Line
date: 2022-09-21 00:08:00
categories: command
---
## Linux

<!--more-->

### 文件操作

* cd /<Path>
  * ==打开文件夹==
* cd ..
  * ==返回上一级文件夹==
* ls
  * ==查看当前路径文件==
* rm -r /<Path>/<FolderName>
  * ==删除文件夹==
* rm -f <FileName>
  * ==删除文件==
* cp /<Path>/<FileName> /<Path>/<NewFileName>
  * ==复制文件&重命名==
* mkdir <FolderName>
  * ==创建文件夹==
* touch <FileName>
  * ==创建文件==
* tar -xvf <FileName>
  * ==解压tar包==
* unzip <FileName> -d <FolderName>
  * ==解压zip包==
* tar -cvf <ArchiveName> <FolderName>
  * ==压缩tar包==
* zip -v <ArchiveName> <FolderName>
  * ==压缩zip包==
  
### 软件操作

* apt-get update
  * ==更新软件源==
* apt-get upgrade
  * ==更新全部软件==
* apt-get upgrade <PackageName>
  * ==更新指定软件==
* apt list --upgradable
  * ==可更新软件列表==
* apt list --installed
  * ==查看已安装的所有软件==
* apt-get install <PackageName>
  * ==安装软件==
* apt-get remove <PackageName>
  * ==删除软件==
* apt-get --purge remove <PackageName>
  * ==删除软件和配置文件==

### 常用命令

* systemctl stop gdm
  * ==关闭图形界面==

* /etc/NX/nxserver --restart
  * ==重启图形界面==


## ROS2

* source /opt/ros/galactic/setup.bash
  * ==获取启动文件==
* printenv | grep -i ROS
  * ==检查环境变量==
* ros2 node list
  * ==查看节点列表==
* ros2 topic list
  * ==查看话题列表==
* ros2 param list
  * ==查看参数列表==
* ros2 run <PackageName> <FileName>
  * ==运行包的可执行文件==
* ros2 node info <NodeName>
  * ==检查节点信息==
* ros2 topic info <TopicName>
  * ==检查主题信息==
* ros2 topic echo <TopicName>
  * ==查看节点数据==
* ros2 interface show <TopicName>
  * ==查看主题期望的数据结构==
* ros2 param get <NodeName> <ParamName>
  * ==查看参数的类型和当前值==
* ros2 param set <NodeName> <ParamName> <Value>
  * ==修改参数当前值==
* ros2 launch <LaunchName>
  * ==打开启动文件==
* ros2 launch <PackageName> <LaunchName>
  * ==打开包中的启动文件==
* ros2 bag record <TopicName>
  * ==记录话题信息==
* ros2 bag record -o <FileName> <TopicName1> <TopicName2>...
  * ==记录多个话题信息==
* ros2 topic hz <TopicName>
  * ==查看话题数据发布频率==
* colcon build
  * ==构建命名空间&构建包==
* colcon build --packages-select <PackageName>
  * ==构建某个包==
* ros2 pkg create --build-type ament_cmake <PackageName>
  * ==创建新包==

## Docker

* docker ps
  * ==查看当前容器的数量和状态==
* docker start <ContainerName> -i
  * ==启动容器并查看容器输出的信息==
* docker stop <ContainerName>
  * ==停止容器==
* docker exec -it <ContainerName> zsh/bash
  * ==进入容器==
* docker cp <ContainerName>:/<Path><FileName> <Path><FileName>
  * ==将容器中的文件复制出来==
* docker cp <Path><FileName> <ContainerName>:/<Path><FileName>
  * ==将文件复制进容器中==



## Git

* git config --global user.name "<Name>"
  * ==配置全局用户名==
* git config --global user.email "<Name>"
  * ==配置全局邮箱==
* ssh-keygen
  * ==获取公钥==
* git init
  * ==初始化==
* git clone <url>
  * ==克隆仓库==
* git add .
  * ==将全部文件放到暂存区==
* git commit -m "<message>"
  * ==将全部文件合并==
* git remote add origin <url>
  * ==连接远程仓库==
* git push origin master
  * ==上传合并的文件==
* git push origin master -f
  * ==强制上传==
* git reset HEAD
  * ==将暂存区的所有文件恢复到工作区==
* git remote rm origin
  * ==删除远程连接==
