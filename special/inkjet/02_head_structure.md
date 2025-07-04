# ② ヘッド構造 (Head Structure of Inkjet Technology)

## 概要

インクジェット技術の中核を成すのがインクを噴射する「ヘッド（printhead）」です。ヘッドの構造設計は、解像度・速度・信頼性・メンテナンス性を大きく左右します。

## ノズルアレイの構成

インクジェットヘッドは多数のノズルで構成されており、高密度に並べられたノズルアレイが高解像度印刷を実現します。

- ノズル径：10～50 µm 程度
- ノズル数：数百〜数千
- 配列：直線、ジグザグ、2次元マトリクスなど

## 材料と製造技術

ヘッドの基板やノズル部にはMEMS技術が使われ、以下のような材料が採用されます。

- **基板材料**：シリコン、ガラス、セラミックス
- **ノズル層**：ポリイミド、SU-8、SiO₂など
- **保護層／撥液処理**：テフロン系コーティングやDLC膜など

製造には以下のようなプロセスが用いられます：

- フォトリソグラフィとエッチングによる微細加工  
- ウェハーレベルでの配線・接合・貫通電極（TSV）技術  

## ヘッドの種類

インクジェットヘッドは駆動方式によって大きく2種類に分けられますが、それぞれ構造が異なります。

- **サーマルヘッド**：ノズルの近傍にマイクロヒーターを配置
- **ピエゾヘッド**：ノズル室の一部に圧電アクチュエータを統合

それぞれにおいてインクの温度管理や材料との相性が重要です。

## ヘッド構造の課題

- ノズル詰まりとクリーニング機構  
- インクの飛翔方向の安定性  
- 経年劣化と信頼性（例：ヒーターの劣化、圧電素子の疲労）

---

※次章では、このヘッドを駆動・制御する回路技術について解説します。
