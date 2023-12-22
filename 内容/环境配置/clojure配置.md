---
layout: default
title: clojure配置
date: 2023-12-20
---

# <center>clojure配置</center>



## emacs-repl环境

## 简介

`REPL` (Read-Eval-Print-Loop)，又称 `interactive toplevel` `交互式顶层构件` ，指称交互式编程环境。

环境：ubuntu22 desktop

## 步骤一，安装依赖项

在bash中，

```bash
sudo apt install clojure
sudo apt install leiningen
```

在emacs中，

```elisp
M-x package-install cider RET
M-x package-install clojure-mode RET
```

## 步骤二，启动clojure-repl环境

命令行使用

```bash
clojure
```

在命令行中进行REPL即可。

emacs 使用

```bash
lein new [app-name]
lein repl
```



```elisp
M-x cider RET
cider-connect-clj RET
localhost RET
[app-name]:port RET
```

在 `cider-repl` 缓冲区中进行 `clojure-repl` 即可。

## 参考 

[Clojure:guides/install-clojure](https://clojure.org/guides/install_clojure)

[Braveclojure: basic-emacs](https://www.braveclojure.com/basic-emacs/)

[Github: clojure-emacs/cider](https://github.com/clojure-emacs/cider)

[维基：读取-求值-输出循环](https://zh.wikipedia.org/wiki/%E8%AF%BB%E5%8F%96-%E6%B1%82%E5%80%BC-%E8%BE%93%E5%87%BA%E5%BE%AA%E7%8E%AF)
