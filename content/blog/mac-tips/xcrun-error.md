---
title: 'How to resolve xcrun error in Mac OS'
date: 2019-11-07 08:19:43
category: 'Mac tip'
---

When you use <strong>GIT</strong> in Max OS, sometimes faced this error message.
~~~
xcrun: error: invalid active developer path (/Library/Developer/CommandLineTools), 
missing xcrun at: /Library/Developer/CommandLineTools/usr/bin/xcrun
~~~

There are many reasons which occur this error. However, this error is occurred mainly due to OS update.
Due to Mac OS update, Xcode Command Line Tools issue is occurred.😢

### How to solve?
Fortunately, you can solve this problem!!!😏<br>
1. Open <strong>Terminal App</strong>
2. Type below command
~~~
xcode-select --install
~~~
3. You should faced alert windows for install command line tool.
4. Click button and start install!!!

#### Reference
> [stack overflow](https://stackoverflow.com/questions/52522565/git-is-not-working-after-macos-update-xcrun-error-invalid-active-developer-pa)