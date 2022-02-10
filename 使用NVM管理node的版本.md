# 使用NVM管理node的版本

#### 下载 [nvm](https://link.segmentfault.com/?enc=QO4qYyRHnDPSvk39amKMRQ%3D%3D.Y1Qhk%2Bq7sH7MOPlccWxUsIqDfkBGY%2FEjwxvXwnOcm%2Bf%2F7iN0Q%2F%2BGz9LvhVjW8A%2BvnAkKiTFDivEB088sRN5tNg%3D%3D)，推荐下载 nvm-setup.zip

下载完成之后一直点击下一步下一步即可安装完成（注意：安装路径不要出现中文名称）

#### 配置

在 nvm 安装根路径找到 setting.txt 加入下载源的设置
```
node_mirror: https://npm.taobao.org/mirrors/node/
npm_mirror: https://npm.taobao.org/mirrors/npm/
```


#### 使用
+ 查看可安装的版本
    `nvm ls available`
+ 安装稳定最新的版本
    `nvm install latest`
+ 安装指定的版本
    `nvm install 14.16.0`
+ 卸载指定的版本
    `nvm uninstall 14.16.0`
+ 切换指定的版本
    `nvm use 14.16.0`

#### 可能会产生的问题
+ 使用nvm下载node时npm不会自动安装
  - 请下载相应的npm包放置在相应node版本下的node_modules文件夹中
  - 改名为npm
  - 复制npm文件夹下的npm、npm.cmd、npx、npx.cmd到相应node版本的文件夹下
 