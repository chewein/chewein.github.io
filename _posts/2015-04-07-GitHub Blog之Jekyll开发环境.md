---
layout: post
author: Chewein
title: GitHub Blog之Jekyll开发环境
category: GitHub
tag: [GitHub,博客,测试,环境] 
---


[Jekyll](http://jekyllrb.com/) is a simple,blog aware,static site generator。
Jekyll就是一个博客生成系统,将博客模块化,解析组织页面之间联系的系统。


##安装Jekyll
###安装Ruby
Jekyll使用Ruby编写的,所以要先配置Ruby环境,通过Ruby安装Jekyll。
去[rubyinstaller](http://rubyinstaller.org/downloads/)下载相应版本安装,安装时有三个选项注意勾选将安装路径添加到环境变量。

安装完成后点击电脑开始->ruby文件夹下有个"start Command Prompt with Ruby"点击输入ruby -v显示对应版本。

如果是直接用电脑的cmd输入ruby则可能显示**no such file or directory**,原因不详！
如果使用cygwin的终端则在.bashrc里添加下面命令才能使用ruby的各个命令。

```
alias gem=’gem.bat’
alias rake=’rake.bat’
alias erb=’erb.bat’
alias irb=’irb.bat’
alias rdoc=’rdoc.bat’
alias ri=’ri.bat’
alias rspec=’rspec.bat’
alias cucumber=’cucumber.bat’
alias bundle=’bundle.bat’
```

###安装DevKit
DevKit是windows平台下编译和使用本地C/C++扩展包的工具,它就是用来模拟Linux平台下的make,gcc,sh来进行编译。此方法目前仅支持通过RubyInstaller安装的Ruby。
在[rubyinstaller](http://rubyinstaller.org/downloads/)页面的下面有DevKit列表选择对应版本下载下来。

- 双击DevKit.exe将其解压缩,并进入解压缩文件夹;
- 打开"start Command Prompt with Ruby",输入下面命令安装Devkit

```
ruby dk.rb init
ruby dk.rb install
``` 

至此Ruby的环境安装完毕。

###安装gem
[RubyGems](https://rubygems.org/pages/download)(简称gems)是一个用于对Ruby组件进行打包的Ruby打包系统,它提供一个分发Ruby程序和库的标准格式,还提供一个管理程序包安装的工具。
RubyGems的功能类似于Linux下的apt-get,Python下的pip/easy-install等工具。
在[RubyGems](https://rubygems.org/pages/download)上介绍了gem的安装过程:
- Download;
- Unpack into a directory and cd there;
- Install with: ruby setup.rb (you may need admin/root privilege)。
要查看的话可以使用命令"ruby setup.rb - -help"。

使用gem安装其他包时候可以指定源:

```
gem sources list                            //查看当前源
gem sources -a http://ruby.taobao.org/      //添加新源
gem sources --remove https://rubygems.org/  //删除旧源
```

当使用gem安装其他包时出现下述问题

```
RROR:  Error installing jekyll:
invalid gem: package is corrupt, exception while verifying: undefined method`path2class' for #<Psych::ClassLoader:0x0000010c9d0be0> (NoMethodError) in /Users/ryan/.rvm/gems/ruby-2.0.0-p353/cache/i18n-0.6.9
``` 

这是因为安装的gem版本不对,解决方法:
- 输入命令gem env找到-GEM PATHS下的目录;
- 删掉上述目录下所有文件;
- 重新安装gem。

###安装jekyll
直接使用命令**Gem install jekyll**就可以安装jekyll了,安装完成之后使用命令"jekyll –version"检查是否安装成功。

------------------------------------

## 使用jekyll 
jekyll –server  
在浏览器里面输入：http://localhost:4000/ 就可以看到你的页面在本地跑起来了。
以后调试就方便多了，不用重复commit push之类的。


------------------------------------

## ISSUE

- jekyll –server时出现cannot load such file -- hitimes
  - gem list检查hitimes的类型是否是mingw32,如果是执行下述命令
  - gem uninstall hitimes
  - Ensure all the versions (ruby and x86-mingw32 are uninstalled)
  - gem install hitimes - -platform=ruby











