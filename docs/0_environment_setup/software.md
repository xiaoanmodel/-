# 作品安装说明
> 阅读此说明，你可以快速安装并使用产品
> 
**支持的设备**：
- HarmonyOS设备
- OpenHarmony设备
## 方法一：快速安装
1. **连接设备**
连接目标设备，并确保设备开启传输文件授权
2. **选择目标设备**
点击顶部菜单栏 运行(R) → 选择设备，从下拉列表中选取已识别的设备
3. **一键构建并安装**
在 IDE 右上方的工具栏中，点击运行按钮
DevEco Studio 将自动完成以下操作：
- 编译当前工程并生成 .hap 安装包
- 通过 hdc 工具将应用部署到目标设备
- 自动启动应用

## 方法二：hdc命令安装
#### 环境准备：
- 确保设备已连接成功
- 已安装hdc工具并配置至系统环境变量
- .hap安装包已构建完成
#### 安装步骤
以下为完整安装流程命令说明：
> 若第一次安装，则跳过步骤1、2
1. **强制停止已有应用**
确保设备中已安装的旧版本应用停止运行，避免干扰安装过程。
```
hdc shell aa force-stop com.diangroup.myapplication
```
2. **卸载旧版本应用**
删除设备中已有的同包名应用，避免版本冲突。
```
hdc uninstall com.diangroup.myapplication
```
3. **创建临时目录用于传输 .hap 文件**
用于存储待安装的 .hap 文件。
```
hdc shell mkdir data/local/tmp/ecf1f6d7f0e24259b77bc932c2abe8b1
```
4. **发送.hap文件到设备**
将本地构建生成的 .hap 文件发送至设备的临时目录。
```
hdc file send D:\repository\cameraPicker\entry\build\default\outputs\default\entry-default-signed.hap data/local/tmp/ecf1f6d7f0e24259b77bc932c2abe8b1
```
5. **安装应用**
```
hdc shell bm install -p data/local/tmp/ecf1f6d7f0e24259b77bc932c2abe8b1
```
1. **删除临时文件**
清理临时目录，释放设备空间。
```
hdc shell rm -rf data/local/tmp/ecf1f6d7f0e24259b77bc932c2abe8b1
```
1. **启动应用**
```
hdc shell aa start -a EntryAbility -b com.diangroup.myapplication
```
