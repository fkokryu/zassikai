# Some models to manage additive consistency and derive priority weights from hesitant fuzzy preference relations

Yejun Xu, Weijia Dai, Jing Huang, Mengqi Li, Enrique Herrera-Viedma  
Information Sciences 586 (2022) 450–467

---

## 1. Introduction

### ファジィ集合、ファジィ選好関係
ファジィ集合は意思決定者（DMs）が自分の好みについて確信が持てない場合や情報が不完全な場合に広く使用される

- Orlovsky
    - ファジィ選好関係（FPRs）の定義を提案  
    しかし、ファジィ集合には意思決定者が判断情報の明確な値を提供することに躊躇する問題を扱う上での限界がある。

- Torra
    - 躊躇ファジィ集合（HFS）という概念を定義  
    HFSはペアワイズ比較行列の要素に0から1の間の複数のメンバーシップ度を適用。さらに、HFSは躊躇ファジィ言語集合に拡張された。

- XiaとXu
    - HFSを基に、躊躇ファジィ選好関係（HFPRs）を提案  
    そして、整合性分析、優先度重要度の導出、不完全HFPRなどHFPRに関する一連の調査

---

### 整合性の研究
- Tanino
    - FPRの整合性

- WangとXu
    - hesitant fuzzy linguistic preference relations (躊躇ファジィ言語選好関係)の概念を定義
    - 加算整合性   
    以下を満たすとき、LPR $ R= (r_{ij})_{n \times n} $ は加算整合性を持つ
    $$
    r_{ij} = r_{ik} + r_{kj}, \forall i, j, k = 1, 2, \dots
    $$
    - 弱整合性  
    以下を満たすとき、LPR $ R= (r_{ij})_{n \times n} $ は弱整合性を持つ  
    $$
     r_{ik} \geq 0.5 \text{ and } r_{kj} \geq 0.5 ならば
     r_{ij} \geq 0.5 , \forall i, j, k = 1, 2, ..., n, i \neq j \neq k
    $$

- Xuら
    - 不完全HFPRに対する加算整合性の概念を提案  

- Liuら
    - HFPRのための新しい整合性とコンセンサスの枠組みを開発

- Zhuら
    - Hesitant Multiplicative Programming Model
    $$
    \begin{align}
    \text{Maximize} \quad f(x) = \prod_{i=1}^n x_i^{a_i} \nonumber \\
    \text{subject to} \quad g_j(x) \leq 0, \quad j = 1, 2, \ldots, \nonumber m
    \end{align}
    $$ 

    ここで、$x_i$ は決定変数、$a_i$ は各変数の重要度を示す係数、$g_j(x)$ は制約条件を表す関数

- MengとAn
    - HFPRの乗法的整合性の検証

- LiとWang
    - 平均整合性に基づくHFPRの新しい加法的整合性の概念を開発  
    すべての可能な組(i,j,k) に対する整合性の評価を平均化し、その平均値を用いてHFPRの整合性を判断。これにより、全体としての整合性が個々の不一致によって過度に影響を受けない
- Rodríguezら
    - 整合性の種類とその意味合い
    - 加算整合性 (Additive Consistency)  
    Linguistic Preference Relation $ R = (r_{ij})_{n \times n} $ は全ての $ i, j, k $ に対して以下の等式が成立する場合、加算整合性を有します。

    $$
    r_{ij} = r_{ik} + r_{kj}, \quad \forall i, j, k = 1, 2, \dots, n
    $$

    - 乗算整合性 (Multiplicative Consistency)  
    Multiplicative Preference Relation $ R = (r_{ij})_{n \times n} $ は全ての $ i, j, k $ に対して以下の等式が成立する場合、乗算整合性を有します。

    $$
    r_{ij} = r_{ik} \times r_{kj}, \quad \forall i, j, k = 1, 2, \dots, n
    $$

    - 弱整合性 (Weak Consistency)  
    Weak Consistency in a Preference Relation $ R = (r_{ij})_{n \times n} $ は全ての $ i, j, k $ に対して以下の不等式が成立する場合、弱整合性を有します。

    $$
    r_{ik} \geq 0.5 \text{ and } r_{kj} \geq 0.5 \implies r_{ij} \geq 0.5, \quad \forall i, j, k = 1, 2, \dots, n
    $$

    - 最適整合性 (Optimal Consistency)  
    最適整合性は具体的な数式で定義するのが難しい場合が多いが、通常は整合性の最大化を目指す最適化問題として表されます。Optimal Consistency in a Preference Relation $ R = (r_{ij})_{n \times n} $ は、複数の整合性評価法を組み合わせて最も高い整合性スコアを得る設定が求められます。一般的な形式は次のようになります。

    $$
    \text{Maximize } C(R) \text{ subject to various consistency constraints}
    $$

    ここで$C(R)$は整合性の計算式で、具体的な形式は使用する整合性指標に依存します。

---

### 既存研究の問題点
- Zhangらによる正規化プロセス：  
Zhangらは加算整合性を有するHFPRの定義を提案、この方法ではHFPRを正規化する必要があるがDMの元の判断を歪めるリスクあり。また異なる正規化方法によって、複数の正規化されたHFPR（NHFPR）が生成される可能性。
- Zhuらによる乗法的整合性の研究：  
Zhuらは楽観的整合性指標を用いてHFPRの乗法整合性を評価したが、この方法では元のHFEに追加の値を入れるb正規化が用いられている。これもDMの元の選好情報を歪める可能性がある。さらに、この手法ではHFPRを最も整合性が高いFPRに変換してしまい、DMの躊躇を適切に反映できない。
- ZhuとXuの研究：  
この手法では、HFPRの整合性が弱い場合や低い場合を無視する傾向にある。これにより、元のHFPRの整合性情報を包括的に反映することができない
- Liらによる区間整合性指標：  
Liらの研究では、区間整合性指標が用いられたが、この指標が意思決定プロセスにおける不確実性を増大させたと報告。

---

### この論文では  
1. **完全加算整合性と弱加算整合性の導入：**
   - HFPRsの整合性を評価するために、完全加算整合性（CAC）と弱加算整合性（WAC）という新しい概念を提案。これらの整合性を測定するために、複数の線形プログラミングモデル

2. **整合性修正方法の開発：**
   - HFPRが加算的に一貫していない場合、整合性を修正するための方法を開発。この方法により、不一致の判断を修正し、加算的に一貫した新しいHFPRを構築。この新しいHFPRは元のHFPRとの間で偏差が最小限に抑える。

3. **優先度重要度の算出：**
   - 整合性のあるHFPRから優先度重要度を求めるために、いくつかの線形プログラミングモデルを設計。これらのモデルでは、正のパラメータ $h$ (h > 1) を導入し、異なる$h$の値によって異なる優先度重要度ベクトルを導出しつつ、ランキング結果が変わらないようにする。さらに、整合性の管理、優先度重要度の取得、および整合性のあるHFPRsの選択肢のランキングを一般化する統合アルゴリズムの提案。

### 既存モデルと比較した場合の提案概念と手法の新規性と利点  
1. **CACとWACの概念：**
   - 完全加算整合性（CAC）と弱加算整合性（WAC）は、表面的な整合性情報だけでなく、潜在的な整合性情報もHFPRs内に含まれている。これにより、元のHFPRの整合性情報を最大限に反映することができる。

2. **整合性の検証方法：**
   - 提案された整合性検証方法は、HFS（Hesitant Fuzzy Sets）に新たな値を加えたり取り除いたりすることなく、意思決定者（DM）の以前の優先情報を歪めることなく、すべての判断情報を考慮に入れるる。0-1混合プログラミングモデルを用いて実現。

3. **整合性のない情報の修正プロセス：**
   - 加算的に一貫した新しいHFPRを構築する際、できるだけ元の情報を保持し、整合性のない情報を修正する。

4. **優先度重要度の導出方法：**
   - 優先度の重要度は、提案された線形プログラミングモデルを使用して、複雑な計算を行うことなく得ることができる。この方法により、整合性のあるHFPRから効率的に優先度重要度を導出することが可能。

5. **整合性メソッドの適用可能性：**
   - 提案された整合性メソッドは、不完全なHFPRsにおける整合性のタイプを検証するためにも応用できる。これにより、整合性が部分的にしか確認できない場合でも、整合性の評価が行える。

---

## 2. Preliminaries

### Fuzzy Preferrence Relations(FPRs)
#### 定義1
Fuzzy Preference Relations（FPRs）は通常、$ n \times n $サイズの行列$ R = (r_{ij}) $によって表され、各要素は以下の条件を満たします：

$$
r_{ij} + r_{ji} = 1, \quad r_{ii} = 0.5, \quad \forall i, j
$$

- $ r_{ij} = 0 $は選択肢$ j $が選択肢$ i $に完全に優先されることを示す。
- $ r_{ij} = 0.5 $は選択肢$ i $と選択肢$ j $の間に差がないことを示す。
- $ r_{ij} = 1 $は選択肢$ i $が選択肢$ j $に完全に優先されることを示す。
- $ 0 < r_{ij} < 0.5 $は選択肢$ j $が選択肢$ i $より明確に優先されることを示す。

以下は加法整合性に関する定義とその理論的議論、リマーク、数値例を含む詳細な説明です：

#### 加法整合性の定義
Fuzzy Preference Relation（FPR）$ R = (r_{ij})_{n \times n} $ が加法整合性を持つとは、すべての $i, j, k$ に対して以下の条件を満たすこと:
$$
r_{ij} = r_{ik} - r_{jk} + 0.5
$$

#### 重要度

**重要度ベクトル**:
FPRが加法的に一貫している場合、非負の要素からなる優先度の重要度ベクトル $ W = (w_1, w_2, ..., w_n)^T $ が存在し、全ての重要度の合計が1になる：
$$
w_i \geq 0, \quad \sum_{i=1}^n w_i = 1, \quad i \in N
$$

**重要度とFPRの関係**:
重要度 $ w_i $ と優先度 $ r_{ij} $ の間の関係は、対数関数を用いて次のように表現できます：
$$
w_i(\theta) = \frac{\theta^{1/n \sum_{k=1}^n r_{ik}}}{\sum_{j=1}^n \theta^{1/n \sum_{k=1}^n r_{jk}}}, \quad r_{ij} = \log_{\theta}w_i - \log_{\theta}w_j + 0.5, \quad \forall i, j \in N
$$
ここで、$ \theta > 1 $ です。$ \theta $ がネイピア数 $ e $ に近づくと、重要度関数は次のように単純化されます：
$$
w_i(e) = \frac{e^{1/n \sum_{k=1}^n r_{ik}}}{\sum_{j=1}^n e^{1/n \sum_{k=1}^n r_{jk}}}, \quad i \in N
$$

**パラメータ $ \theta $ の影響**:
任意のパラメータ $ \theta > 1 $ に対して、優先度の重要度 $ w_i(\theta) $ は次を満たします：
$$
w_i(\theta) = \frac{(w_i(e))^t}{\sum_{j=1}^n (w_i(e))^t}, \quad t = \ln\theta, \quad \forall i, j \in N
$$
この式は、パラメータ $ \theta $ が重要度の分布を調整できることを反映しており、任意の正の $ \theta $ に対して、$ w_i(\theta) $ は単に $ w_i(e) $ の $ e $ を底とする累乗変換。

#### 備考1
特定の $ \theta $ の値に関係なく同じランキング順序を維持する。


#### 数値例

以下のようなFPR行列 $ R $ を考えます:
$$
R = \begin{bmatrix}
0.5 & 0.8 & 0.7 \\
0.2 & 0.5 & 0.4 \\
0.3 & 0.6 & 0.5 \\
\end{bmatrix}
$$
重要度 $ w_1, w_2, w_3 $ が $ h $ とともに変動することが示されます。これらの変動にもかかわらず、ランキング順序 $ w_1 > w_3 > w_2 $ は、$ h $ が1から10,000に増加するにつれて一貫している。

#### 定義3
意思決定者により与えられた$ R = (r_{ij})_{n \times n} $に抜けがあっても、与えられているすべての要素で以下が成り立てば加法整合性を持つ
$$
r_{ij} = r_{ik} - r_{jk} + 0.5
$$

---
### Hesitant Fuzzy Sets（HFS）
DMの判断情報のためらいと不確実性を説明するために、TorraはHFSを定義

**定義4** 有限集合X上のHFSは、[0, 1]内の非空の有限値部分集合を返す関数h(x)によって記述できます。HFSは次のように定義されます：
$$
E = \{(x, h(x)) \> x \in X\}
$$
ここでh(x)はXの要素xがHFS Eに属する可能性のあるメンバーシップ度を示し、h(x)は躊躇ファジー要素（HFE）と呼ばれます。

**定義5** h(x)がHFEである場合、その上限と下限は以下のように示されます：
$$
h^+(x) = \max h(x)
$$
$$
h^-(x) = \min h(x)
$$

---
### Hesitant Fuzzy Preference Relations（HFPR）
FPRとHFSに基づいて、XiaとXuがHFPRを提案。
しかし、その定義ではHFSの値が昇順であることが必要で、DMの元の優先情報が歪められてしまうことがあり、これらの欠点を克服するために、XuらはHFPRの改訂された定義を提案しました。

#### 定義6
集合X上のHFPRは、行列 $ H = (h_{ij})_{n \times n} \subseteq X \times X $ によって表され、ここで $ h_{ij} = \{ h_{ij}^l \} | l = 1, 2, ..., \#h_{ij} $（\#h_{ij} は $ h_{ij} $ の要素数）はHFEです。$ h_{ij} $ は選択肢 $ x_i $ が $ x_j $ を上回る全ての可能な優先度を示し、$ h_{ij} $ は次の条件を満たす必要があります：

$$
h_{ij}^l + h_{ji}^{(\#h_{ij}-l+1)} = 1, l = 1, 2, ..., \#h_{ij}
$$
$$
h_{ii} = \{0.5\}, i \in N
$$
$$
\#h_{ij} = \#h_{ji}, \forall i, j \in N
$$

ここで $ h_{ij}^l $ は $ h_{ij} $ の $ l $ 番目の要素です。

#### 定義7
$ H = (h_{ij})_{n \times n} $ をHFPRとし、$ h_{ij} = \{ h_{ij}^l | l = 1, 2, ..., \#h_{ij} \} $ の場合、一部の要素がDMによって提供されない場合、それらは記号 "-" で示され、他の要素はDMによって満たされるべきであり、$ H $ は不完全なHFPRと呼ばれます：

$$
h_{ij}^l + h_{ji}^{(\#h_{ij}-l+1)} = 1,
$$
$$
h_{ii} = \{0.5\},
$$
$$
\#h_{

ij} = \#h_{ji},
$$

ここで $ h_{ij}^l $ は $ h_{ij} $ の $ l $ 番目の要素で、すべての $ h_{ij} $ ∈ EVに対して、ここでEVは $ H $ における全ての既知のHFEの集合です。

---

## 3. Some methods of consistency test, inconsistency modification and weights derivation for HFPRs

### 3.1. Two types of additive consistency of HFPRs

CACとWACはともに、元のHFPRから加法整合性を満たすFPRを導出できる。  
CAC：加法的整合性FPRのすべての値がHFPRのHFEから導かれる  
WAC：加法的整合性FPRのすべての値がHFPRのHFEの下界と上界の間の範囲にある

#### 定義8.
HFPR $ H = (h_{ij})_{n \times n}, h_{ij} = \{ h_{ij}^l \} _{l = 1,2,...,\#h_{ij}} $があり、次の条件を満たす FPR $ R = (r_{ij})_{n \times n} $ が存在する場合、完全加法的一貫性のあるHFPRと呼ばれます:

$ r_{ij} = r_{ik} - r_{jk} + 0.5, r_{ij} \in h_{ij}, \forall i,j,k \in N  $

明らかに、定義8で提示された一貫性情報は、$ H $における対応するHFEから直接得られます。言い換えれば、加法的一貫性のあるFPRはHFPRから導出することができます。しかし、DM（意思決定者）の有界合理性のために達成することは困難です。場合によっては、対応するHFEの上限と下限の範囲内に含まれる要素を持つ加法的一貫性のあるFPRが存在するかもしれません。このインスタンスでは、提供されたHFPRも加法的一貫性情報を含んでいると考えます。したがって、HFPRのための新しいWAC（弱い加法的一貫性）の定義を提案します。

---

#### 定義9.
HFPR $ H = (h_{ij})_{n \times n}, h_{ij} = \{ h_{ij}^l \} _{l = 1,2,...,\#h_{ij}} $ に対して、$ H $内の加法的一貫性のある FPR $ R = (r_{ij})_{n \times n} $ が存在し、次の条件を満たす場合、弱い加法的一貫性のあるHFPRと呼ばれます:

$ r_{ij} = r_{ik} - r_{jk} + 0.5, h_{ij}^- \leq r_{ij} \leq h_{ij}^+, \forall i,j,k \in N  $

ここで、$ h_{ij}^- $ と $ h_{ij}^+ $ はHFE $ h_{ij} $ の下限と上限です。

---

定理1に触発されて、弱い加法的一貫性のあるHFPRの等価な定義は以下のとおりです:

#### 定義10.
HFPR $ H = (h_{ij})_{n \times n}, h_{ij} = \{ h_{ij}^l \} _{l = 1,2,...,\#h_{ij}} $であり、正規化された重みベクトル $ W = (w_1, w_2, ..., w_n)^T $, $ \sum_{i=1}^n w_i = 1 $, $ w_i \geq 0 $, $ i \in N $ およびパラメータ $ \theta > 1 $が存在する場合、弱い加法的一貫性のあるHFPRと呼ばれます。そこで、

$ h_{ij}^- \leq \log_{\theta} w_i - log_{\theta} w_j + 0.5 \leq h_{ij}^+, \forall i,j \in N $

---

HFPRの対称性に従って、HFPRのためのWACの等価な定義を得ることができます。

#### 定義11.
HFPR $ H = (h_{ij})_{n \times n}, h_{ij} = \{ h_{ij}^l \} _{l = 1,2,...,\#h_{ij}} $が、正規化された重みベクトル $ W = (w_1, w_2, ..., w_n)^T $, $ \sum_{i=1}^n w_i = 1 $, $ w_i > 0 $, $ i \in N $ およびパラメータ $ \theta > 1 $が存在し、次の条件を満たす場合、弱い加法的一貫性のあるHFPRと呼ばれます:

$ h_{ij}^- \leq log_{\theta} w_i - log_{\theta} w_j + 0.5 \leq h_{ij}^+ ,i = 1,2,...,n - 1, j = i + 1,...,n $

---

#### 備考2
定義8より、与えられたHFPRには可視的な加法的整合的FPRが存在し、これはDMが提供する選好がある程度合理的であることを示す。よって、HFPRから合理的一貫性のある情報を抽出することができる。定義9は、HFPRにおける暗黙的一貫性判断を考慮し、DMの元情報から論理的情報を導出しようとするものである。定義8と9から、HFPRがCACであればWACでなければならないが、その逆ではないことは明らかである。

---

#### 備考3
HFPRは、完全加法的整合HFPR、弱加法的整合HFPR、加法的無矛盾HFPRの3種類に分けられる。CACはWACの特殊なケースであると結論づけられる。すなわち、あるHFPRが完全に加法的整合的である場合、それは弱加法的整合的でなければならず、その逆はありえない。

---

### 3.2. Consistency test for HFPRs