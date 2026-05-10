# Agentic Engineering Strategy
[日本語](index.md) | [English](index_EN.md) | [GitHub](https://github.com/stakiran/agentic-engineering-strategy)

## はじめに

### Agentic Engineering とは？
2025 年に Vibe Coding を唱えた Andrej Karpathy が、2026 年版のあり方として唱えたもの。

- <https://x.com/karpathy/status/2019137879310836075>

人間が直接コードを書くことはほとんどない。かわりに AI に任せ、人間は AI、特にエージェント群をオーケストレーションし、その動きを監督するのがメインとなる。また、この営みには深みがあり、再現性を持たせられる余地もありそうである。

このような「次に来そうな潮流」の名前は未定だが、Karpathy は「Agentic Engineering」が好みだとポストした。また 99% の時間をオーケストレーションと監督に使うことや、エンジニアリングには技と理論と（習得すべき）専門性があるといったニュアンスも書いている。

このドキュメントでは、次のように定義しよう:

Agentic Engineering とは、**人間がコードを全く書かないか、ほとんど書かずに、かわりに AI エージェントに任せる潮流** である。

Agentic Engineering の特徴は、その名が示すとおり二点ある:

- エージェントの名前があるとおり、生成 AI を「エージェント」なる単位でとらえて任せること
- エンジニアリング（工学）とあるとおり、工学として整備できるだけの知見が揃っている or 揃いつつあること

マネージャーは自ら手を動かさず、部下という複雑な人間を上手くマネジメントするが、同様に、Agentic Engineering は私たち自らがマネージャーとなり、AI エージェントという部下を上手くマネジメントせねばならない。かつ、この営みは、体系化できるか、できそうなくらいの水準にまで来ている。

わかりやすいのは Prompt Engineering だろう。この手の教科書や論文は多数存在する。Agentic Engineering も今後そうなっていくだろうが、 2026-05-10 現在は未整備である。

### Agentic Engineering Strategy とは？
本題に入ろう。

Agentic Engineering Strategy とは、Agentic Engineering を実現するための **AI エージェントのアーキテクチャ案** を指す。パターンと呼ぶほどの具体性と有効性はなく、概念モデルのレベルで、このような概念と関係性を据えれば上手くいく（かもしれない）、という案を述べている。つまりは戦略である。あるいはアプローチと言っても良い。

Agentic Engineering Strategy の目的は、この営みを志す同志に、参考とインスピレーションを与えることだ。

## このドキュメントの読み方
