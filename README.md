﻿访问 [Release 页面](https://github.com/Ludoux/LRCHelper/releases)来获得最新的发布版本，或者手动编译代码尝鲜(但通常二进制文件与源代码所对应) 

-----

**编译要 Json90r1 的支持(引用了Newtonsoft.Json),dll是Net45版本.运行要.NET Framework4.5.2的支持**

针对网易云音乐开发，根据提供的歌曲ID或歌单ID自动下载整理歌词包括翻译的功能，顺便为  SONY®WALKMAN® 设计了翻译延迟1秒的功能.

## 写在前面

最基本功能是实现了，在之后的时间会完善代码，包括：

* 继续完善 SharedFramework 的功能，整理代码，注意其与其他类的功能差别.
* Tag的更具体的支持.
* 完善安全性，作为插件动态加载.

## 具体操作方法(Release 版本)

(目前版本去除了手动模式，若有需要烦请 Release 页面下载 Pre-release 的v0.0.0-beta 版本).

在AUTO-SET功能开启时，可以直接复制其对应的链接(ex http://music.163.com/#/song?id=461332109 )，软件在切入前台时会自动填充，

或者手动输入对应的ID号并选择ID所对应的含义(Music or Playlist)

然后点击按钮"GET".

1. 若为是音乐ID，lrc文件(UTF-8)会在软件所处目录下生成，结束时会在 Status 处显示详情.
2. 若为是歌单ID，lrc文件(UTF-8)会在软件所处目录的以歌单名命名的文件夹中生成，结束时会在 Status 处显示详情，更具体信息请查看生成的 Log.txt 文件.

## Tips:

1. 翻译比外文歌词慢一秒.但你可以更改方法调用的参数.
2. 目前歌词歌单仅支持网易云.在很久远的未来会以附加组件的方式进行弥补.
3. 不支持同行多个时间轴，且没有异常处理.

## TO DO:

1. 更改UI.
2. 继续封装，完善代码安全性和可维护性.
3. 增加歌曲信息，歌词信息等.
4. 特别久远的就是写其它的歌词文件处理方法.

## License:

在 MIT 协议下发布.

## 参考&感谢:

获取外文歌词的代码基于 ituff 的[163lyric项目](https://github.com/ituff/163lyric)的实现，进行了修改.(但是ituff并没有指定那个项目的开源协议)

感谢 Moonlib.com 的所有人 Moon 在这个博客上发表了[自己整理的API](http://moonlib.com/606.html).

## 更新信息(最近在上)

* 2017.3.12 可以取消(Cancel)操作了(#Weekly)(v1.0.2 #Release)
* 2017.3.11 更改了核心代码——允许空白歌词(含翻译)存在，对翻译处理更大度，更改了对于翻译是否存在的实现，修复了一个经常发生关于延迟修复的bug.注意cancel仍有问题.(#Weekly)
* 2017.2.17 删除一无用方法，进入代码优化阶段.(#Weekly)
* 2017.2.12 新增了Auto-Set功能，使用更方便.(#Weekly)
* 2017.2.5  允许取消操作，有BUG，使用Task实现UI和下载线程分离，修复LICENSE编码错误，不稳定的代码版本.
* 2017.2.4  使用了TPL类库实现了并行循环下载@Playlist 模式，速度较原先提高了(效果因设备而异)；优化代码，Fix Bugs.(v1.0.1 #Release)
* 2017.1.25 粗略的代码重构，重写了实现.未广泛测试.(v1.0.0 #Release)
* 2016.9.2  Fix Bugs.(v0.0.0-beta #Release)
* 2016.8.30 Log文件内容实现对齐，AUTO实现执行线程与UI线程分离，可实时看进度与错误数.
* 2016.8.29 初版.