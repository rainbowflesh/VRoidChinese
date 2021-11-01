# VRoidChinese

VRoid 汉化插件

## 特性

- 运行时对软件进行汉化, 不修改软件本体。
- 通过配置文件进行文本配置

## 使用方法

#### 安装

1. 下载 Releases 中的最新版本
2. 解压到软件根目录, 解压之后的目录结构如下 (标星号\* 的为汉化插件, 请确保路径正确)

```
|-VRoid Studio
  |-BeplnEx*                  BeplnEx 框架
    |-config
      |-BepInEx.cfg           BeplnEx 的设置文件
  |
  |-Chinese*                  汉化资源文件夹
    |-MessagesChinese.json    汉化文件
    |-StringChinese.txt       汉化文件
  |
  |-MonoBleedingEdge          软件的资源文件夹
  |
  |-VRoidChinese*             汉化插件
    |-..                      一些 .cs 文件
  |
  |-VRoidStudio_Data          软件的资源文件夹
  |
  |-VRoidStudio.exe           启动软件的执行文件
  |
  |-doorstop_config.ini*      汉化插件配置
  |
  |-winhttp.dll*              汉化插件依赖
  |
  |-..                        乱七八糟的文件们
```

4. GIF 图示

![image](https://github.com/xiaoye97/VRoidChinese/blob/master/VRoidStudioChineseInstallTutorial.gif)

#### 更新翻译

1. 若插件本身未更新, 但是翻译有更新, 则从仓库下载 Chinese 文件夹, 并覆盖软件根目录中的 Chinese 文件夹.

## 问题排查

##### 因软件更新导致的汉化失效? 提交 issue 提醒开发人员.

##### 出现了不可名状的 bug? 提交 issue 提醒开发人员! 并汇报插件运行日志.

(日志文件定位:%RootLetter%:\install location...\VRoid Studio\BepInEx\LogOutput.log)

ps:

在..BepInEx\config\BepInEx.cfg 中可以修改日志等级,如果你希望你的 issue 能够得到更有用的回复, 或者帮助开发人员了解 bug 的详细, 请根据此文件内的提示把日志记录等级开到最大.

##### 不知道为什么汉化失效?按照 Q&A 进行自我排查

### Q&A

Q:

我的 vroid 是 steam 上下载的, 在一次更新后汉化失效, 完全无法在 vroid 欢迎页面选择到中文! 我要如何解决?

A:

1. 检查 GitHub 上插件是否更新, 若更新请在 release 中下载最新版本, 在文件目录中**覆盖**之前的文件. 若无效, 请参考下一条.
2. 尝试重新安装插件, 甚至重新安装软件后安装插件. 若无效, 请参考下一条.
3. 下载使用集成了插件的 vroid 软件, 例如~~<https://share.weiyun.com/TSkcpf9I>~~. 若无效, 请参考下一条.
4. 定位到 c:\用户\你的用户名\AppData\LocalLow\pixiv\VRoid Studio\Player.log
   浏览此文件, 若存在如下字段

   ```
   ...
    <RI> Initialized touch support.
    UnloadTime: x.xxxxxx ms
   ...
   ```

   且在此之后没有看到任何形如

   ```
   [Message:   BepInEx] BepInEx 5.4.17.0 - VRoidStudio
   [Info   :   BepInEx] Running under Unity v2020.3.19.6877495
   ```

   的字段出现, 请按照以下流程进行解决:

   ```
   * 删除位于 c:\用户\你的用户名\AppData\LocalLow 下的pixiv文件夹, 即上述Player.log所在的父目录.
   * 卸载vroid软件及汉化插件 (直接删除也行).
   * 重新启动计算机.
   * 安装vroid软件及汉化插件.
   * done!
   ```

5. 待续, 任何问题请积极提交.

## 帮助翻译/校对

1. 编辑 BepInEx/config/VRoid.Chinese.cfg, 可以打开开发者模式, 用来 Dump 英文原文和运行时切换原文.
2. 使用外部文本编辑器, 如 VSCode, 记事本等打开 Chinese 文件夹下的两个文本.
3. 对照英文原文进行翻译/校对.
4. 运行 VRoid Studio 进行测试.
5. 确认无误后, 提交 PR 或者直接反馈给我 (QQ:1066666683 VRoid 交流群:684544577).
