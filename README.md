---

# 📘 edusemi v3.0 - 半導体基礎教育資料

edusemi は、半導体デバイス、プロセス技術、SoC設計、パッケージ・テスト、デザインレビューまで、  
実務的な視点と教育的構成を両立したオープンな基礎教材群です。  
現場経験に基づく「体系的かつ実用的」な教育を目指し、初学者から若手技術者、社会人のリスキリングまで幅広く活用できます。

---

## 📑 目次

0. [第0章：半導体物性の基礎](#第0章半導体物性の基礎)
1. [第1章：デジタル基礎とMOSトランジスタの原理](#第1章デジタル基礎とmosトランジスタの原理)  
2. [第2章：半導体プロセスの歴史と進化](#第2章半導体プロセスの歴史と進化)  
3. [第3章：0.18μmプロセスとMOSトランジスタ特性](#第3章018μmプロセスとmosトランジスタ特性)  
4. [第4章：SoC設計基礎と設計フロー](#第4章soc設計基礎と設計フロー)  
5. [第5章：テスト・パッケージ・製品化](#第5章テストパッケージ製品化)  
6. [第6章：デザインレビューと開発組織連携](#第6章デザインレビューと開発組織連携)  
7. [🌟 特別編（special）](#-特別編special)  
8. [📜 半導体の歴史（history）](#-半導体の歴史history)  
9. [🧭 今後の展開（v2x-以降）](#-今後の展開v2x-以降)  
10. [🧩 応用展開edusemi-plus](#-応用展開edusemi-plus)  
11. [🎯 対象読者](#-対象読者)  
12. [📝 ライセンスと引用について](#-ライセンスと引用について)  
13. [👤 作成者・連絡先](#-作成者連絡先)
    
---


## 第0章：半導体物性の基礎

- 半導体とは何か：バンド構造と電子の振るまい  
- シリコン結晶とドーピング：N型／P型の形成  
- キャリアの生成・移動・再結合  
- PN接合の空乏層と順・逆バイアス応答  
- ダイオードのI-V特性と応用（LED・ツェナー・太陽電池など）  
- MOSトランジスタへの導入的な理解  
🔗 関連資料: [chapter0_semiconductor_basics/](chapter0_semiconductor_basics/)

---

## 第1章：デジタル基礎とMOSトランジスタの原理

- 2進数と論理演算の基本  
- 論理回路と真理値表  
- インバータの回路動作と波形理解  
- MOSトランジスタの構造と役割  
🔗 関連資料: [chapter1_digital_mos/](chapter1_digital_mos/)

---

## 第2章：半導体プロセスの歴史と進化

- プロセス微細化の流れと技術背景  
- 0.35μm〜0.13μm世代の特徴（STI, サリサイド, Cu配線など）  
- FinFET、GAAなどの先端構造  
- 微細化に伴う課題と材料技術の変遷  
🔗 関連資料: [chapter2_process_history/](chapter2_process_history/)  
🔗 詳細な歴史解説: [history/](history/)

---

## 第3章：0.18μmプロセスとMOSトランジスタ特性

- 0.18μmの技術的意義と実務性  
- トランジスタ構造、設計ルール、DRC例  
- バラツキと信頼性の設計対応  
🔗 関連資料: [chapter3_cmos018/](chapter3_cmos018/)  
🔗 実測データ・解析資料: [data/](chapter3_cmos018/data/)

---

## 第4章：SoC設計基礎と設計フロー

- SoC構造と仕様定義  
- 抽象設計からIP選定、PDK運用  
- RTL → 物理設計 → マスク設計の流れ  
🔗 関連資料: [chapter4_soc_design/](chapter4_soc_design/)

---

## 第5章：テスト・パッケージ・製品化

- ウェハテストと良否判定  
- パッケージ技術（BGA/QFN/COF）  
- ファイナルテストと信頼性試験  
🔗 関連資料: [chapter5_test_package/](chapter5_test_package/)

---

## 第6章：デザインレビューと開発組織連携

- DRの基本思想と目的  
- フェーズ別DRの役割  
- プロセス・品質保証との連携強化  
🔗 関連資料: [chapter6_design_review/](chapter6_design_review/)

---

## 🌟 特別編（special）

半導体技術の応用・発展領域に関する教材です。基礎教材に加え、先端プロセス・EDA自動化・メモリ・制御理論・材料応用まで幅広くカバーしています。

- 🔧 [PDK Documentation Hub](special/pdk/)  
- 🛠️ [EDA自動化と設計演習](special/eda/)  
- 📡 [アナログ／ミックスドシグナル／RF設計](special/ams/)  
- 💾 [メモリ技術入門](special/memory/)  
- 🧪 [Advanced Process Analysis](special/advanced_process/)  
- 📦 [パッケージ技術と実装解析](special/package/)  
- 🧠 [LLM×制御ハイブリッドASIC設計](special/llm_control_asic/)  
- 🖨️ [インクジェット技術](special/inkjet/)

---

## 📜 半導体の歴史（history）

- 序論：なぜ「半導体の歴史」が重要か  
- 真空管と電子制御の前史（〜1940年代）  
- トランジスタの発明とその意義（1947年〜）  
- ICと集積化の進展（1958年〜）  
- MOS革命とムーアの法則（1960〜70年代）  
- メモリ時代と日本半導体の躍進（1970〜80年代）  
- ULSIとグローバル競争（1990〜2000年代）  
- ポストスケーリングの新時代（2000年〜現在）  
- 地政学・政策・再興への展望  
🔗 詳細資料: [history/](history/)

---

## 🧭 今後の展開（v3.x 以降）

- 🔁 Sky130 + OpenLane による RTL → GDS 設計実習  
- 🐍 Python による設計解析・自動化  
- 📊 0.18µm CMOS 実測データを活用した教材化  

---

## 🧩 応用展開：edusemi-plus

基礎教材に加え、産業応用・人材育成・政策提言に対応した拡張教材です：

- 半導体産業と人材戦略の関係性  
- 教育・企業・地域連携の具体モデル  
- スマート農業、地域DX、災害対応などの応用  
- 教育政策との連携提案  

👉 [edusemi-plus GitHubページはこちら](https://github.com/Samizo-AITL/edusemi-plus)

---

## 🎯 対象読者

- 半導体・回路・設計の初学者  
- 新人エンジニア・大学生・高専生  
- リスキリング・研修を受ける社会人  
- 教育機関・企業研修講師

---

## 📝 ライセンスと引用について

- 本資料は **MITライセンス** で公開されています  
- 教育目的での再利用・改変・引用は自由ですが、**出典の明記**をお願いします

---

## 👤 作成者・連絡先

**三溝 真一（Shinichi Samizo）**  
半導体デバイス技術エンジニア

- GitHub: [https://github.com/Samizo-AITL](https://github.com/Samizo-AITL)  
- Email: shin3t72@gmail.com  
- Twitter: [@shin3t72](https://twitter.com/shin3t72)

---

## 📘 改訂履歴（ChangeLog）

| バージョン | 日付       | 主な変更点                                                                 |
|------------|------------|------------------------------------------------------------------------------|
| v3.0       | 2025-07-03 | 🔹 第0章「半導体物性の基礎」を正式追加<br>🔹 第1章を論理中心に再構成<br>🔹 トップREADMEの目次・構成を全面見直し |
| v2.0       | 2025-06-15 | 🔹 章構成と教材群を体系化（第1章〜第6章 + 特別編 + history）<br>🔹 各章にREADMEと.md教材を導入 |
| v1.0       | 2025-06-01 | 🔹 初期教材試作・GitHub展開開始|

> 🛠 以後の更新は GitHub の commit log または [Releases] ページを参照してください。
>
---

