---
title: 【ROS2教程】安装(基于Ubuntu24.04)
date: 2025-10-14 01:06:40
tags: ROS
---

## ROS是什么

**ROS**是一个适用于机器人的开源的元操作系统。它提供了操作系统应有的服务，包括硬件抽象、底层设备控制、常用函数的实现、进程间消息传递、包管理以及用于获取、编译、编写、和跨计算机运行代码所需的工具和库函数。

## ROS的安装

ROS 目前有三个版本：

- ROS 2 Kilted Kaiju
- ROS 2 Jazzy Jalisco
- ROS 2 Humble Hawksbill

在后面我们采用第二个版本即 ROS 2 Jazzy Jalisco 来进行安装。官方推荐的硬件环境为Ubuntu Linux 24.04，本文也是采用这个环境。

在开始之前，请确保你系统的`locale`支持UTF-8，你可以通过下面的命令来查看：

```bash
locale
```

### 为什么选择 Jazzy Jalisco

- 是最新的LTS（长期支持）版本
- Moveit2官方推荐

### 启用所需要的Repositories

```bash
sudo apt install software-properties-common
sudo add-apt-repository universe
```

```bash
sudo apt update && sudo apt install curl -y
export ROS_APT_SOURCE_VERSION=$(curl -s https://api.github.com/repos/ros-infrastructure/ros-apt-source/releases/latest | grep -F "tag_name" | awk -F\" '{print $4}')

curl -L -o /tmp/ros2-apt-source.deb "https://github.com/ros-infrastructure/ros-apt-source/releases/download/${ROS_APT_SOURCE_VERSION}/ros2-apt-source_${ROS_APT_SOURCE_VERSION}.$(. /etc/os-release && echo ${UBUNTU_CODENAME:-${VERSION_CODENAME}})_all.deb"

sudo dpkg -i /tmp/ros2-apt-source.deb
```

### 安装开发工具（可选）

```bash
sudo apt update && sudo apt install ros-dev-tools
```

### 安装ROS 2

在这里我们选择安装Jazzy Jalisco这个版本，简称`jazzy`

```bash
sudo apt update && sudo apt upgrade
sudo apt install ros-jazzy-desktop
```

### 激活你的ROS环境

`ros2`虽然已经被安装了，但还未添加到环境变量，因此不可使用。我们可以使用下面的命令激活`ros2`环境：

```bash
source /opt/ros/jazzy/setup.bash
```

> 如果你的终端使用的其他shell（如zsh）请将setup末尾的bash替换为对应shell

方便起见，我们在`~/.bashrc`文件中添加这个命令，以在每次启动终端时自动启用ROS环境。

```bash
echo "source /opt/ros/jazzy/setup.bash" >> ~/.bashrc
```

## Congratulations

恭喜你，成功安装了ROS2的开发环境!😆😆😆



