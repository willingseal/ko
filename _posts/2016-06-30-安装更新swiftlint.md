---
layout: post
title: "安装更新swiftlint"
categories:
- Other
tags:
- Other


---


### SwiftLint 
是一个用于强制检查 Swift 代码风格和规定的一个工具，基本上以 [GitHub's Swift 代码风格指南](https://github.com/github/swift-style-guide)为基础。

### 安装 swiftlint
```
➜  ~ brew search swiftlint
swiftlint
Error: GitHub API Error: API rate limit exceeded for 61.49.105.18. (But here's the good news: Authenticated requests get a higher rate limit. Check out the documentation for more details.)
Try again in 21 minutes 43 seconds, or create a personal access token:
  https://github.com/settings/tokens/new?scopes=&description=Homebrew
and then set the token as: export HOMEBREW_GITHUB_API_TOKEN="your_new_token"
➜  ~ export HOMEBREW_GITHUB_API_TOKEN="afeab1e439be9ecb5adddddddd463c5"
➜  ~ brew search swiftlint
swiftlint
➜  ~ brew install swiftlint
==> Downloading https://homebrew.bintray.com/bottles/swiftlint-0.10.0.el_capitan
######################################################################## 100.0%
==> Pouring swiftlint-0.10.0.el_capitan.bottle.tar.gz
🍺  /usr/local/Cellar/swiftlint/0.10.0: 48 files, 15.2M
➜  ~ brew list
carthage    swiftlint
➜  ~ swiftlint version
0.10.0
```

### 更新swiftlint版本
- 查看brew版本号，更新brew版本
- 查看安装的包列表，查看包是否需要更新
- 更新某个包／全部更新
- 删除老的包


```
➜  Brienne git:(master) brew outdated          查看你的包是否需要更新
➜  ~ brew list
➜  Brienne git:(master) brew list --versions          查看你安装过的包列表
carthage 0.16.2
swiftlint 0.10.0
➜  Brienne git:(master) brew upgrade swxftlint     更新某个包swxftlint
Error: swiftlint 0.10.0 already installed

➜  Brienne git:(master) brew -v
➜  Brienne git:(master)  brew --version          查看brew版本
Homebrew 0.9.9 (git revision b2c96; last commit 2016-06-02)
Homebrew/homebrew-core (git revision a74a; last commit 2016-06-03)
➜  Brienne git:(master) brew update          更新brew
Updated Homebrew from b2c9625 to cab97cf.
Updated 1 tap (homebrew/core).
==> New Formulae
。。。

➜  Brienne git:(master) brew --version          查看brew版本（对比老的版本看看）
Homebrew 0.9.9 (git revision cab97; last commit 2016-06-27)
Homebrew/homebrew-core (git revision 44de; last commit 2016-06-29)
➜  Brienne git:(master) brew list --versions
carthage 0.16.2
swiftlint 0.10.0

➜  Brienne git:(master) brew outdated          查看你的包是否需要更新
carthage (0.16.2 < 0.17.1)
swiftlint (0.10.0 < 0.11.1)
➜  Brienne git:(master) brew upgrade          更新包（所有的）
==> Upgrading 2 outdated packages, with result:
carthage 0.17.1, swiftlint 0.11.1
==> Upgrading carthage
。。。
➜  Brienne git:(master) brew list --versions
carthage 0.16.2 0.17.1
swiftlint 0.10.0 0.11.1
➜  Brienne git:(master) brew cleanup          清理旧版本的包缓存（Homebrew 将会把老版本的包缓存下来）
Removing: /usr/local/Cellar/carthage/0.16.2... (44 files, 11.7M)
Removing: /usr/local/Cellar/swiftlint/0.10.0... (48 files, 15.2M)
==> This operation has freed approximately 26.9M of disk space.
➜  Brienne git:(master) brew list --versions
carthage 0.17.1
swiftlint 0.11.1

```


