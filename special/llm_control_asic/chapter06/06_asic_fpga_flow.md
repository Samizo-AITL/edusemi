# 第6章 ASIC設計とFPGA検証フロー（詳解）

## 6.1 FPGA設計と検証の役割

### 6.1.1 FPGAプロトタイプの目的

- 設計したRTLが仕様通り動作するかを早期に検証  
- 実機環境に近い条件でシステム全体の挙動を確認  
- 問題発見・修正のサイクルを高速化

### 6.1.2 FPGA検証の主な手法

- シミュレーション（RTLシミュレータ）  
- 実機書き込みによる動作確認  
- ロジックアナライザ・ILAによる信号観測

---

## 6.2 ASIC設計フロー概要

### 6.2.1 プロセスノードの選定

- 性能（クロック周波数）、消費電力、製造コストを考慮  
- 先端ノード（5nm〜7nm）から成熟ノード（28nm〜65nm）まで選択肢多様  
- ファウンドリの提供するPDKに適合させる必要あり

### 6.2.2 PDK（Process Design Kit）

- ファウンドリが提供する設計ガイドライン・セルライブラリ・モデル一式  
- 物理設計・DRC/LVSチェックで必須  
- PDKのバージョン管理が設計品質に直結

---

## 6.3 ASIC設計主要工程

### 6.3.1 論理合成（Synthesis）

- RTLからゲートレベルネットリスト生成  
- 性能・面積・消費電力のトレードオフを調整

### 6.3.2 配置配線（Place & Route）

- 論理合成結果を物理セルに配置  
- 配線経路を決定しクロック遅延や配線遅延を最適化

### 6.3.3 DRC（Design Rule Check）・LVS（Layout vs Schematic）

- ファウンドリの設計ルール違反がないか検証  
- レイアウトと回路図の一致を確認

### 6.3.4 STA（Static Timing Analysis）

- タイミングパスを解析しクロック制約を満たすか評価  
- ボトルネックの特定と調整を行う

### 6.3.5 GDSファイル生成

- 最終的なレイアウトデータをGDSII形式で出力  
- ファウンドリへの製造用データとして送出

---

## 6.4 製造後の評価とフォローアップ

- 実機チップの機能確認・性能測定  
- 不具合解析・リビジョン設計の検討  
- テストプラン・信頼性評価の実施

---

## まとめ

FPGA検証からASIC設計、製造準備までの一連の流れを詳細に解説しました。  
設計の各段階で求められる品質管理とツールの役割を理解し、実際のチップ開発に役立ててください。  

---

> 次章では、実機評価や検証のポイント、品質保証について扱います。
