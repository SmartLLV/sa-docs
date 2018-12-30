---
layout: default
title: 物理架构云上部署 .travis.yml 文件编写与使用
---
# Travis-CI
{:.no_toc}

* 目录
{:toc}

## 前提条件
- Github 账户
- Github 项目所有权

## 入门步骤
1. 首先进入 [Travis-CI](https://travis-ci.com/) 官网，使用 Github 账号进行注册；
2. 接受 Travis-CI 的授权申请（会被重定向至 Github）；
3. 点击绿色的**激活**按钮，选择想在 Travis-CI 上使用的仓库（repository）；
4. 在仓库中，添加一个 `.travis.yml` 文件，用来告诉 Travis-CI 具体需求；
5. 把 `.travis.yml` 添加到 git，提交并推送，从而触发一次 Travis-CI 构建（_只有在你添加 .travis.yml 后，Travis 才会构建你所推送的提交_）；
6. 检查构建状态页面，查看构建结果是成功还是失败。

## 支持语言

    Android
    C
    C#
    C++
    Clojure
    Crystal
    D
    Dart
    Erlang
    Elixir
    F#
    Go
    Groovy
    Haskell
    Haxe
    Java
    JavaScript (with Node.js)
    Julia
    Nix
    Objective-C
    Perl
    Perl6
    PHP
    Python
    R
    Ruby
    Rust
    Scala
    Smalltalk
    Swift
    Visual Basic

> [Travis-CI 完整编程语言支持列表（英文）](https://docs.travis-ci.com/user/languages/)

## 参考文档
1. [Getting started - Travis CI](https://docs.travis-ci.com/user/getting-started/)

