---
title: ペンディングHEAD
tags: [version control]
---

2007/4/26



諸君、私は[継続的インテグレーション](http://www.objectclub.jp/community/XP-jp/xp_relate/cont-j)が大好きだ。
シンプルなプラクティスが開発チームに甚大な影響を与えるのが好きだ。
だがあらゆるプラクティスがそうであるように、欠陥^H^H^H^Hカイゼンの余地がある。
[Paul Duvall](http://www.testearly.com/category/duvall/)（{{isbn '0321336380','まもなく出版される継続的インテグレーション本'}}の著者）がこの点について[指摘](http://www.testearly.com/2007/04/25/the-future-of-continuous-integration/)していた。
コミットビルドが失敗すると、チーム全体に影響し、それが修正されるまでスピードが落ちてしまう。



ThoughtWorksで継続的インテグレーションを始めた頃、
そのやり方について心配していたことがあった。
ThoughtWorks 2000のスタイル（訳注：2000年頃のやり方）と
[C3]]プロジェクトで使っていたスタイルが違っていたからだ。



ThoughtWorks 2000スタイルは、今日使われているような通常の継続的インテグレーションスタイルである。
成果に満足したらレポジトリにコミットし、ビルドマシーンでビルドする（あるいは、CruseControlなどのCIサーバで手動でビルドする）。
問題は、誤ったコードをコミットしてしまい、
それが修正されるまで、アップデートすると欠陥コードが出てくるということだ。



C3流ではレポジトリのHEADに直接コミットしない。
C3はSmalltalkのプロジェクトで、Envy（Smalltalk指向レポジトリシステム）を使っていた。
Envyは主流のレポジトリとは少しコンセプトが異なっている。
ずいぶん昔のことなので、どういう動きをしていたか記憶が定かではないが、
基本的に、作業中は「エディション」にコミットすることになる。
これはプライベートなブランチのようなものだ。
みんなに見えるが、干渉はされない。
ビルドマシンでビルドに成功したときだけ、
エディションを「リリース」にアップグレードする。
これはブランチではなくメインラインに相当する。
この方法だと、壊れたコードをプロジェクトのメインラインに入れてしまうことは決してない。



Envyだとこのような使い方が簡単にできる。
今日のバージョン管理システムでは、少しトリッキーにならざるを得ない。
理想を言えば、ワーキングコピーを作って、
アップデートはHEADから行って同期するようにしておき、
コミットは別のHEAD（ペンディングHEAD）にコミットする。
そして、インテグレーションビルドに成功したときだけ真のHEADにコミットする。
継続的インテグレーションサーバは
ペンディングHEADからチェックアウトして、
ビルドに成功したら、真のHEADにコミットする。



こういったものを自分でセットアップするのは難しいのだろうか？
すでにやったことのあるチームがいるが、まだ話していないのでよく分からない。
だが、いくつかのチーム指向のツールを使って、同等のことができる。
たとえば、JetBrainの[[TeamCity](http://www.jetbrains.com/teamcity/)では「遅延コミット」と呼ばれている。
また、PaulがBorlandのGauntletについて言及している。



他にも、これがどれだけ重要なのかという疑問もある。
2000年における私の心配は杞憂で、我々はビルドが失敗してもペンディングHEADを採用ほどダメージを受けることはなかった。
ビルドが失敗しても、それを直す方法は他にもある。
問題なのは、コミットする前に自分のところでビルドしないことだ。
毎度のことだが、複雑な技術を導入する前に考えなければいけないのは、
人の問題なのである。