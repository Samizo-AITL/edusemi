# 📡 EMI・EMCの基礎と対策設計

---

## 📝 はじめに

近年のSoCやパッケージでは、動作周波数の高速化・多機能化に伴い、**EMI（電磁干渉）**および**EMC（電磁適合性）**が重大な設計課題となっています。特に、**高速信号ラインやクロック系統、電源ノイズ**は、パッケージ内部でも強い電磁放射源となりえます。

---

## 📖 EMI・EMCとは

- **EMI（Electromagnetic Interference）**  
  他の回路やシステムに悪影響を与える「**電磁ノイズの放射**」

- **EMC（Electromagnetic Compatibility）**  
  周囲のノイズに「**耐性があり、かつ自分もノイズを出さない**」という性能指標

---

## ⚠️ パッケージ内における EMI の発生源

| 発生源 | 主な原因 | 波形特性 |
|--------|----------|----------|
| クロック系統 | 高速立ち上がりエッジ | 高周波スパイク成分 |
| 電源/GNDノイズ | デカップリング不足 | 低周波〜広帯域 |
| 信号反射・リターン電流 | インピーダンス不整合 | 突発的なノイズ成分 |
| LDO/スイッチング電源 | スイッチングトランジェント | 周期的ノイズ、ハーモニクスあり |

---

## 📡 解析と測定手法

- **EMシミュレーション**（3Dフィールド解析）  
  - 電場・磁場の分布を空間解析（例：Ansys HFSS, CST）
  - パッケージ構造＋基板配線をモデル化
  - EMI放射のホットスポットを可視化可能

- **SPICE/IBISによる高速信号モデル評価**  
  - ドライバと伝送線路の結合によるノイズ評価
  - リターンパス制御の有無で波形差異を確認

- **測定装置例**  
  - EMIプローブ、スペクトラムアナライザ、EMIチャンバー

---

## 🧰 EMI抑制設計テクニック

| 対策項目 | 内容 |
|----------|------|
| **GNDプレーンの連続性** | リターン電流の通り道を確保し、共通インピーダンスを下げる |
| **信号線のペア配置** | 差動信号やクロック線を対称配置し、放射を打ち消す |
| **デカップリングキャパシタ** | 電源ラインのノイズ吸収（近距離配置が重要） |
| **フェライトビーズ／EMIフィルタ** | 高周波ノイズの選択的除去 |
| **EMIシールド** | メタルケースや樹脂コーティングによる外部放射遮断 |

---

## 📷 EMIホットスポットの例（概念図）

```
┌──────────────┐
│    Package     │
│ ┌────────────┐ │
│ │   Si Die     │ │ ← クロック源やPLLからの放射が強い
│ └─────▲──────┘ │
│       │ 放射パス          │
│ ┌─────┴──────┐ │
│ │ Substrate / PCB │ ← GNDの断続により放射経路が形成
└────────────────┘
```

---

## 🧠 EMI解析の演習課題（例）

1. 高速クロック（200MHz）のラインを持つパッケージについて、GND配置の工夫でEMIを抑えるにはどうするか？
2. 反射がEMIに与える影響をSPICEシミュレーションで確認せよ。
3. Ansys HFSSでパッケージ構造の電界分布をシミュレーションする手順をまとめよ。

---

## 📎 EMC試験と規格（参考）

| 規格名 | 内容 |
|--------|------|
| CISPR 22 / 32 | 放射ノイズ・伝導ノイズの許容範囲 |
| IEC 61000-4 | イミュニティ試験（静電気・サージなど） |
| JEITA規格（EMC-GUIDE） | ICレベルEMI対策ガイドライン |

---

## 🔗 関連ファイル・資料

- 応力と熱の影響 → [`05_stress_simulation.md`](./05_stress_simulation.md), [`04_thermal_analysis.md`](./04_thermal_analysis.md)
- パッケージ構造と電源設計 → [`chapter5_test_package/`](../../chapter5_test_package/)

---

## 🛠️ 推奨ツールリンク

- [CST Studio Suite – 3D EMC解析ツール](https://www.3ds.com/products-services/simulia/products/cst-studio-suite/)
- [Ansys HFSS – 高周波電磁界解析](https://www.ansys.com/products/electronics/ansys-hfss)

---
