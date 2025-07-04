
# 1.4: MOSトランジスタの構造と原理

---

## ✅ MOS構造の基本

MOSトランジスタ（**Metal-Oxide-Semiconductor Field Effect Transistor**）は、電界でチャネルを制御する**電圧制御スイッチ**です。

| 部位     | 役割                           | 備考                       |
|----------|--------------------------------|----------------------------|
| ゲート（Gate）   | 電圧でチャネル形成を制御        | 絶縁膜（SiO₂）上の金属電極     |
| ソース（Source） | 電流の出入り口（流れ出し側）     | 実質的な**電子の出発点**     |
| ドレイン（Drain）| 電流の出入り口（流れ込み側）     | **電子の到達点**           |
| バルク（Bulk）   | 基板（n型 or p型）               | 通常は**ソースと同電位**に接続 |

> 💡 MOSは**電流を流すのではなく、電界（Gate電圧）でチャネルを開閉**する点が特徴。

---

## ✅ nMOSとpMOSの違い

| 項目       | nMOS型                     | pMOS型                     |
|------------|-----------------------------|-----------------------------|
| 基板       | p型（電子が多数キャリア）     | n型（正孔が多数キャリア）   |
| ゲート条件 | Vg > Vth（しきい値）         | Vg < Vth（負のしきい値）     |
| 電流方向   | **D → S（電子）**            | **S → D（正孔）**            |
| プル系統   | プルダウン（GND方向）         | プルアップ（Vdd方向）        |
| 動作時の極性 | ゲートに正電圧               | ゲートに負電圧               |

---

### 補足図（簡易）

```
nMOS構造（p型基板）

    Gate (金属)
      |
    -----
    SiO₂ (絶縁膜)
    -----
      |
  [Source] —— チャネル（電子） —— [Drain]
      |
     Bulk (p型基板接地)
```

---

## ✅ 動作原理（スイッチとして理解）

MOSFETの動作は、「**チャネルが形成されるかどうか**」で決まります。

### nMOSの例：

- **Vg < Vth** → チャネル非形成（OFF）→ 電流流れない
- **Vg > Vth** → チャネル形成（ON）→ 電流流れる（D→S）

### pMOSの例：

- **Vg > Vth** → チャネル非形成（OFF）
- **Vg < Vth** → チャネル形成（ON）

---

### イメージ：

```
       [Drain]
           |
       ┌───┐
       │   │ ← 電流流れる (ON)
       └───┘
           |
       [Source]
```

→ ゲート電圧のON/OFFで、まるで**電気スイッチ**のようにチャネルが開閉される。

---

## ✅ 電気的特性（導入）

MOSは「電圧で制御し、電流を流す」ため、**入出力電圧/電流の特性**が重要です。

| パラメータ        | 意味                      | 備考                      |
|-------------------|---------------------------|---------------------------|
| Vth（しきい電圧）  | チャネルが形成され始める電圧 | MOSごとに異なる             |
| Id（ドレイン電流） | 流れる電流量               | Vgs, Vdsに依存             |
| Vgs                | ゲート-ソース間電圧        | チャネルの開閉に関係        |
| リーク電流（Ileak）| OFFでもわずかに流れる電流   | サブスレッショルドなどで発生 |

> 📌 Vth・Id・リーク電流の詳細は、**後章（1.6〜）で回路モデルや測定例とともに学習**します。

---

## ✅ Pythonによる動作の簡易シミュレーション

論理的なnMOS動作を模した簡易コード：

```python
def nmos_switch(vg, vth=1.0):
    if vg >= vth:
        print("チャネル形成（ON）：電流が流れます")
    else:
        print("チャネルなし（OFF）：電流は流れません")

# テスト
nmos_switch(0.5)  # OFF
nmos_switch(1.2)  # ON
```

---

## ✅ まとめ

| 観点        | 内容                                      |
|-------------|-------------------------------------------|
| 構造        | Gate/Source/Drain/Bulk＋絶縁膜（SiO₂）     |
| 動作原理    | 電界によってチャネルを形成＝スイッチ動作   |
| n/pの違い   | キャリア種別・ON条件・電流方向が異なる     |
| MOSの強み   | 電圧制御で消費電力が少なく高密度に集積可能 |
