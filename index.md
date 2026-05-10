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

## このドキュメントの意図と読み方

### 興味のある概念モデルを読み進めてもらいたい！
このドキュメントでは、概念モデルを n 点提示する。

たとえば HASIO や OHAT といった名前がついており、HASIO は Harness/Agent/Skill/Input Context/Output Contract から成るし、OHAT は Orchestration/Harness/Agent/Tool から成る。つまり概念単位をいくつか定義した上で、それらの関係性を構築している。

現時点で、どのモデルが正しい・正しくないといったことはわからない。むしろ、意思決定の問題だろう。

**あなたは、あなたのチームは、製品は、どんな概念モデルをつくるべきか。また、なぜそうつくるのか。**

この問いを抱き、歩み続けることこそが最重要なのだと思う。このドキュメントは良きヒントになるはずだ。

### なぜ概念モデルか？
概念単位自体は、読者にとっても馴染みがあるはずだ。たとえば次のような単位はよく登場する:

- Harness
- Agent
- Skill

私事だが、私は Agentic Engineering よりも野心的な取り組みをしている。FASD(Fully Autonomous Software Development) と名付けており、さらに 12 Factor Agents のノリで [12 Factor FASD(Fully Autonomous Software Development)](https://stakiran.github.io/12-factor-fasd/) も整理した。つまり私は Agentic Engineering も含め、実践はもちろん、研究をしている立場でもある。

私は次第に **Agentic Engineering においてもアーキテクチャが重要** と感じるようになった。というのも、単にエージェントを雑に使うだけでは、とても品質など確保できないし、何ができて何ができないかの計測および説明責任も果たせない。にもかかわらず、現時点では、各エンジニアは己の感性に委ねるか、ビジネスよろしく手数を増やすか、もしくはオープンソースのエージェント・ハーネスのフレームワークの試用とキャッチアップに明け暮れている。

たぶん、逃げてはいけないのだ。優秀なマネージャーが信念をもって仕組みをつくるように、私たちも Agentic Engineer もそうせねばならない。アーキテクチャという言葉が便利だろう。アーキテクチャをつくる、と言えば通じやすい。では、Agentic Engineeirng におけるアーキテクチャとは？

私は、まず必要なのは **「わかりやすさ」と「とっかかり」** だと考えた。そこで、シンプルに概念単位とその関係を考えることにした。これを概念モデルと呼んでおり、このドキュメントは概念モデルのカタログである。

ちなみに、概念単位としては、すでによく知られたものを持ってきている。しかし多義語ではあるため、各モデルにて意味をしっかりと定義する。

## Agentic Engineering Strategy v0.1

### HOAST
- Harness
    - Orchestration
        - Agent
            - Skill
                - Tool

### OHAST
- Orchestration
    - Harness
        - Agent
            - Skill
                - Tool

### OHAT
- Orchestration
    - Harness
        - Agent
            - Tool

### HASK
- Harness
    - Agent
        - Skill
        - Knowledge

### RHAS
- Remuda
    - Harness
        - Agent
            - Skill

### HASIO
- Harness
    - Agent
        - Skill
            - Input Context
            - Output Contract
