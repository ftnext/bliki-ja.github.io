---
title: コードがドキュメントだ
tags: [agile, documentation]
---

http://www.martinfowler.com/bliki/CodeAsDocumentation.html

アジャイル手法はプログラミングをソフトウェア開発の中心的役割に押し上げた、とよく言われる——ソフトウェア エンジニアリング コミュニティがやってるようなことよりもずっと優秀だよなあ。
プログラミングが中心的役割となったのは、コードをソフトウェア システムにおける「（最）重要なドキュメント」と位置付けたことが理由なんだと思う。

おっと、よく誤解されるので先に反論しておこう。
先ほどの「コードは重要なドキュメントだ」という原則だけど、
「コードが"唯一の"ドキュメントだ」とは言ってない。
「XPではコードがドキュメントだ」とよく耳にするけど、
XPのリーダー達がそんなことを言ってるのは聞いたことがないなあ。
コードを補完するには、他にもドキュメントが必要なんだ。

なぜコードが重要なドキュメントなのかというと、
詳細かつ正確なドキュメントはコードしかないからだ
——この点はJack Reevesの有名な論文『[What is Design?（設計とは？）](http://www.developerdotstar.com/mag/articles/reeves_design_main.html)』（[一つ目の論文の日本語訳](http://www.biwa.ne.jp/~mmura/SoftwareDevelopment/WhatIsSoftwareDesignJ.html)）で指摘されている。

コードがドキュメントなら、プログラマがコードをクリアで読みやすくするよう努力することが重要となる。
「コードがドキュメントだ」ということは、「特定のコードが良いドキュメントだ」ということじゃない。
どんなドキュメントでもそうだけど、コードだってクリアにもなれば、ごちゃごちゃになることもある。
コードだから他のドキュメントよりもクリアになる、ということもない。
（他のドキュメントも絶望的なくらい不明瞭になることがある——以前、どうしようもないUML図を見たことがあったなあ。
(「死んだ馬に鞭打つ」じゃなくて)「人気のある馬に鞭打つ」って感じだけど。）

もちろん、多くのコードは良いドキュメントとは言えないかもしれない。
だけど、コードがドキュメントだからって、
他のドキュメントは認めないと結論付けるのは間違いだ。
同様に、コードはよく貧弱なドキュメントになるから、
コードは「必然的に貧弱なドキュメントになってしまうものだ」と結論付けるのも間違いだ。
だって、クリアなコードを書くことだってできるのだから。
私はどんなコードだってもっとクリアにできると思っているよ。

コードが読みにくいのは、
コードのことを真剣にドキュメントとして扱ってないからじゃないだろうか。
コードをクリアにしようという気がなければ、勝手にクリアになるわけがない。
コードをクリアにするための第一のステップは、
「コードはドキュメントである」と受け入れることだ。
それから、コードをクリアにしようと努めること。
諸悪の根源は、プログラムを始めた頃に教えられたことにまで遡るのかもしれない。
私の先生達はコードをクリアにすることをあまり強調していなかった。
重要視してなかったようだし、その方法についても話してくれなかったしね。
業界全体としては、もっとコードがクリアなことの価値を強調すべきだと思うよ。

次のステップは、コードをクリアにする方法を学ぶことだ。
まずは、売れっ子作家によるアドバイスを紹介しよう——レビューってほどじゃないけど。
私は、多くの人に読んでもらって、フィードバックを得てからじゃないと、
本を出版しようとは思わない。
コードも同様に、何が分かりやすいのか、何が分かりにくいのかという
フィードバックをみんなから得ることが一番重要なんだと思う。
チャンスがあれば、みんなにコードを読んでもらえるようにしよう。
それで、どこが分かりやすいのか、どこが混乱させているのかを見つけ出すんだ。
（そう、そこでペアプロですよ。）

もっと具体的なアドバイスをすると
プログラミング スタイルに関する良書を読むといいだろう。
まず『{{isbn('489100455X','Code Complete'}}』は読んどくべきだ。
当然、『{{isbn('4894712288','リファクタリング')}}』も推薦しておこう
——結局、リファクタリングってのは、コードをクリアにするってことなんだ。
『リファクタリング』の次は、当然『{{isbn('4822282384','パターン指向リファクタリング入門')}}』だ。


これから、いろんな点で反対する人に出会うかもしれない。
だけど、これは覚えておいて欲しい。
「コードはチームの所有物である」（細切れのコードは個人の所有物であってもだ）。 
プロのプログラマというのは、チームのために自分のスタイルを曲げる覚悟があるんだ。
たとえ三項演算子が好きでも、チームが分かりにくいと感じたなら、使わない。
自分スタイルのプログラミングは、個人プロジェクトでやればいい。
チームでやるときは、チームの要望に従わなくちゃ。


*2006-05-18 (木) 12:13:52 通りがかり : 『Code Complete』のリンク先が妙な具合になっているような・・・
*2005-03-24 (木) 17:54:48 ''[[steven.y]]'' : チームでやるときは、チームの必要性に従わなくちゃ -→ チームでやるときは、チームの要望に従わなくちゃ