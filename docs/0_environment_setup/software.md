# 作品安装说明
>
> 阅读此说明，你可以快速安装并使用产品

---

## 客户端安装说明

### 支持设备

- HarmonyOS 设备  
- OpenHarmony 设备  

### 方法一：快速安装（推荐）

1. **连接设备**  
   确保设备已开启文件传输权限，并通过 USB 成功连接。

2. **选择目标设备**  
   点击顶部菜单栏：`运行 (Run)` → `选择设备`，在下拉列表中选择已识别的设备。

3. **一键构建并安装**  
   点击 IDE 右上方的运行按钮，`DevEco Studio` 将自动完成以下操作：

   - 编译当前工程生成 `.hap` 安装包  
   - 通过 `hdc` 工具部署至目标设备  
   - 自动启动应用程序

### 方法二：使用 hdc 命令行安装

#### 环境准备

- 确保设备已连接成功  
- 安装并配置好 `hdc` 工具至系统环境变量  
- 已构建 `.hap` 安装包  

#### 安装步骤

> *若为首次安装，可跳过步骤 1 和 2*

1. **强制停止旧应用（如已安装）**

```bash
hdc shell aa force-stop com.diangroup.myapplication
```

2. **卸载旧版本应用**

```bash
hdc uninstall com.diangroup.myapplication
```

3. **创建临时目录用于传输 .hap 文件**

```bash
hdc shell mkdir data/local/tmp/ecf1f6d7f0e24259b77bc932c2abe8b1
```

4. **发送 .hap 文件到设备**

```bash
hdc file send D:\repository\cameraPicker\entry\build\default\outputs\default\entry-default-signed.hap data/local/tmp/ecf1f6d7f0e24259b77bc932c2abe8b1
```

5. **安装应用**

```bash
hdc shell bm install -p data/local/tmp/ecf1f6d7f0e24259b77bc932c2abe8b1
```

6. **删除临时文件**

```bash
hdc shell rm -rf data/local/tmp/ecf1f6d7f0e24259b77bc932c2abe8b1
```

7. **启动应用**

```bash
hdc shell aa start -a EntryAbility -b com.diangroup.myapplication
```

---

## 服务端安装说明

### 项目概述

本项目包含两个已构建好的 Docker 镜像，并通过 Docker Compose 进行配置与管理。请按照以下步骤安装和运行服务端。

### 安装步骤

#### 安装 Docker 和 Docker Compose

- Docker 官方安装指南：  
  [https://docs.docker.com/get-docker](https://docs.docker.com/get-docker)

- Docker Compose 安装指南：  
  [https://docs.docker.com/compose/install](https://docs.docker.com/compose/install)

验证是否安装成功：

```bash
docker --version
docker-compose --version
```

#### 加载 Docker 镜像

- 下载镜像打包文件 `project_images.tar`，并使用以下命令加载至本地：

```bash
docker load -i <path/to/your_image.tar>
```

> 请将 `<path/to/your_image.tar>` 替换为镜像文件的实际路径。

验证镜像是否成功加载：

```bash
docker images
```

#### 使用 Docker Compose 启动服务

在包含 `docker-compose.yml` 的目录下执行：

```bash
docker-compose up -d
```

- `-d` 表示容器在后台运行  
- 会自动创建容器并运行所有服务  

查看运行状态：

```bash
docker-compose ps
```
