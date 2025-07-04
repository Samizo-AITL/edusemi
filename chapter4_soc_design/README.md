# 第4章：SoC設計基礎と設計フロー

---

## ✅ 本章の目的

- SoC（System on Chip）の基本構成・役割を理解する  
- 製品仕様の解釈から、RTL → 論理合成 → 物理設計 → マスク作成までの**設計フロー全体**を学ぶ  
- PDK（Process Design Kit）の内容と**実務での活用方法**を把握する  
- 教育的に「SoC設計の勘所」を体系的に整理する

---

## ✅ 各節の構成

| 節 | 内容 |
|----|------|
| [4.1](4.1_soc_basics.md) | SoCの基本概念と製品仕様の捉え方 |
| [4.2](4.2_module_ip.md) | モジュール選定と抽象設計（IP設計の利点） |
| [4.3](4.3_pdk_usage.md) | PDKの役割と重要性（設計ルール、モデル、検証条件） |
| [4.4](4.4_design_flow.md) | 設計フロー（RTL → 論理合成 → 物理設計 → 検証 → マスク） |

---

## ✅ 本章の学習で得られること

- **設計上流〜下流の全体像**を俯瞰できる  
- 各工程における役割と成果物（spec, RTL, netlist, layout, GDS）が整理できる  
- プロセス（PDK）と設計の接続関係を明確に理解できる  
- 実務上の**チーム設計、レビュー、設計マージン設計**の基礎が身につく  

---

## 🔧 教材背景

| 項目 | 内容 |
|------|------|
| **想定プロセス** | 0.18μm CMOS（教育・アナログ混載向け） |
| **設計対象** | デジタルSoC（制御系、通信制御、アナログ統合あり） |
| **教育スタンス** | 抽象設計 → 実装設計 → 物理設計まで段階的に理解する |

---

## ⏭️ 次のステップ

以下の順で各節を学習してください：

1. 📘 [4.1：SoCの基本概念と製品仕様の捉え方](4.1_soc_basics.md)  
2. 🧩 [4.2：モジュール選定と抽象設計](4.2_module_ip.md)  
3. 🛠️ [4.3：PDKの役割と重要性](4.3_pdk_usage.md)  
4. 🔄 [4.4：設計フロー（RTL → マスク設計）](4.4_design_flow.md)  

---

📎 第3章（0.18μmプロセス）の理解を土台として、SoC設計の実践的な構成へつなげていきます。
