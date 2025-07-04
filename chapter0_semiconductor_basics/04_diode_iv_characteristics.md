# 04. ダイオードのI-V特性と応用

## はじめに

本章では、PN接合の応用である**ダイオード**の動作特性を具体的に学びます。  
指数関数的な電流の立ち上がり、逆バイアスでの電流遮断、実測データとの対応などを確認し、基本的な応用回路への展開も触れます。

また、**Pythonを使って理想ダイオードのI-V特性を描画**する演習も紹介します。

---

## 1. ダイオードの基本構造と記号

ダイオードは、PN接合そのものです。  
記号は以下のように表されます：
```
  │▶│
 ─┼─▶─┼─
  P   N
```
- アノード：P型側
- カソード：N型側
- 電流は「▶」の向き（順方向）のみに流れる

---

## 2. I-V特性の定量式（理想ダイオード式）

ダイオードの順方向電流は以下の式で近似されます：
I = I₀ × (exp(qV / nkT) − 1)

- I：電流
- V：端子間電圧
- I₀：逆飽和電流（10⁻¹² A程度）
- q：電荷（1.6×10⁻¹⁹ C）
- k：ボルツマン定数（1.38×10⁻²³ J/K）
- T：絶対温度（K）
- n：理想係数（実デバイスでは1〜2）

---

## 3. 特性グラフと挙動

### ◉ 順方向（Pに＋、Nに−）

- 電圧が0.6〜0.7V（Siダイオード）を超えると急激に電流増加
- 指数関数的な立ち上がり

### ◉ 逆方向（Pに−、Nに＋）

- 微小な逆方向電流（リーク）が流れるのみ
- ブレークダウン電圧に達すると急激に電流が増加（ツェナー／雪崩）
```
  ↑ I
│
│            ／
│         ／
│       ／
│─────┬────────→ V
│     │
↓     │
（逆）→ 微小なリーク
```
---

## 4. PythonでI-V特性を描いてみよう

以下は、理想ダイオードのI-Vカーブを描画するPythonスクリプトです：

`plot_diode_iv.py`

```python
import numpy as np
import matplotlib.pyplot as plt

# 定数
q = 1.6e-19     # 電子の電荷 [C]
k = 1.38e-23    # ボルツマン定数 [J/K]
T = 300         # 温度 [K]
n = 1.0         # 理想係数
I0 = 1e-12      # 逆飽和電流 [A]

# 電圧範囲
V = np.linspace(-0.5, 0.8, 500)

# 電流計算
I = I0 * (np.exp(q * V / (n * k * T)) - 1)

# プロット
plt.figure()
plt.plot(V, I, label="Diode I-V")
plt.yscale('log')  # 対数スケールで見ると逆電流も可視化
plt.xlabel("Voltage [V]")
plt.ylabel("Current [A]")
plt.title("Ideal Diode I-V Characteristic")
plt.grid(True)
plt.legend()
plt.show()
```

### 実行結果のポイント

- **順方向領域**では、電圧が0.6〜0.7V（シリコンダイオード）を超えると電流が急激に増加します。これは指数関数の形を反映しています。
- **逆方向領域**では、電流は−I₀に漸近し、ほぼ一定の逆飽和電流が流れるだけです。
- **温度を上げる（T↑）**と、曲線の立ち上がりが早くなり、しきい値電圧が下がります。これは温度依存性の学習にも役立ちます。
- **対数スケール表示**によって、逆電流側の微小変化も可視化できます（実測ではノイズ・リーク要因も見える）。

---

## 5. ダイオードの実用例

| 応用回路        | 内容                                                     |
|-----------------|----------------------------------------------------------|
| 整流回路        | 交流を直流に変換する電源回路の基本構成。全波・半波整流に使われる。 |
| クランプ回路    | 信号の電圧レベルを制限する。保護素子や通信回路に活用。           |
| スイッチング用途 | 高速オン／オフの整流素子としてデジタル回路に組み込まれる。       |
| LED（発光ダイオード） | 順方向バイアスで電子と正孔が再結合し、光を放出する素子。色は材料に依存。 |
| フォトダイオード | 光が当たるとキャリアが生成され、電流が発生。光センサや通信に使用。     |
| ツェナーダイオード | 一定の逆電圧でブレークダウンを起こし、定電圧源として使用される。        |

---

## 6. 理想特性と実測特性の違い

実際のダイオードは、理想式から以下のような差異があります：

### ◉ 実測で見られる非理想性

- **直列抵抗成分**：高電流領域でV-I特性が曲線ではなく直線に近づく
- **逆方向リーク電流**：理想的には0に近いが、表面欠陥や界面準位で増加
- **温度依存性**：逆飽和電流 I₀ は温度上昇とともに急増する（n型・p型共に）

### ◉ 実務上の意義

- 実測カーブから**しきい値電圧、リークレベル、温度安定性**を推定可能
- **プロセスのばらつき**や**品質の定量評価**にも利用される
- ESD保護や信頼性設計での重要指標になる

---

## 7. 次章へのつながり

本章では、PN接合から構成されるダイオードの**理論的I-V特性と実用的な波形・応用例**を確認しました。  
次の章 `05_diode_applications.md` では、このダイオード構造を活かした各種応用素子：

- **発光ダイオード（LED）**
- **ツェナーダイオード**
- **フォトダイオード**
- **太陽電池（ソーラセル）**

などの動作原理と構造の違いを見ていきます。
