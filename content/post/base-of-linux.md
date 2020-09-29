---
title: Linuxカーネルの基礎
date: 2020-09-29
description: Markdown Syntax test page
---

# Linuxカーネルの基礎
## Linuxカーネルとは何か

OSはコンピュータのハードウェアとソフトウェアを管理するソフトウェアの集合である。
OSのうち中核を担うのがカーネルである。カーネルは植物内部にある「仁」のことで種子の内部の核に見立てている。
カーネルが担当する領域はOSによって異なるが、メモリ管理やプログラムの実行制御は多くのOSでカーネルが担う設計になっている。
Linuxはデバイスドライバやネットワークなどもカーネルの担当領域であり、カーネルの領域が広いOSである。このよう担当領域が広いカーネルを**モノシリックカーネル**という。逆にカーネルの担当領域を小さくしたものにGNU HurdやMINIXといったOSがあるが、これらのようなカーネルを**マイクロカーネル**という。

```mermaid
graph TB
    User(ユーザーやアプリケーション) --> SystemCall
    User(ユーザーやアプリケーション) --> FileSystem
    User(ユーザーやアプリケーション) --> Task
    User(ユーザーやアプリケーション) --> Memory
    User(ユーザーやアプリケーション) --> Other
    subgraph OS
        Other(その他のソフトウェア)
        subgraph カーネル
            SystemCall(システムコール):::kernalElement
            FileSystem(ファイルシステム):::kernalElement
            Task(タスク管理):::kernalElement
            Memory(メモリ管理):::kernalElement
        end
    end



style OS fill:#9df,height:240px
style Other fill:#9ef,height:120px
classDef kernalElement fill:#9ef;
```

