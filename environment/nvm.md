# windows下的nvm安装和使用

## 一、查看本地的node，有则卸载
- 1.win+r 
- 2.输入cmd，回车
- 3.输入`node -v`，回车
  - 若输出版本号，表明已经安装过node
    - 卸载node
  - 若显示node不是内部或外部命令，则未安装node
如果是在官网下载的node安装包

## 二、下载安装nvm
- 1.官网下载nvm  
  - [链接](https://github.com/coreybutler/nvm-windows/releases)  
  - 选择 nvm-setup.exe，点击下载
- 2.安装nvm
  - 点击exe文件进行安装，下一步即可
  - 注意储存的路径，有必要可自定义
- 3.安装完成在终端输入`nvm v`，输出版本号即安装成功

## 三、安装node
- 1.`nvm install 16.14.2` 安装指定版本node
- 2.`nvm use 16.14.2` 使用16.14.2版本的node
- 3.`node -v` 查看node版本
- 4.`npm -v` 输出版本号，表明可以正常使用

## 四、常见问题
1.之前安装过node，现在使用nvm管理，终端输入`node -v`显示`"node"不是内部或外部命令`
- 解决方法：环境变量的配置
  - 右击**我的电脑**，选择**属性**，选择**高级系统设置**，选择**环境变量**
  - 会有两个变量
    - `NVM_HOME` : 对应nvm的安装目录
    - `NVM_SYMLINK` ：对应nodejs的安装目录，**若安装的目录没有这个文件夹，手动添加一个**
  - 在**Path变量**里新增这两个环境变量(有则不需要添加）%NVM_HOME% ，%NVM_SYMLINK%
  - 重启终端，即可正常使用
2. 下载包很慢
- 解决方法：配置淘宝镜像
    - ` npm config set registry http://registry.npm.taobao.org/ `
