# 「検索技術」学期末レポート
No:22X3037

## 1. 分析の目的
飲食物の化学特性と味がどのように関係するか、 データを用いて分析するとともに、実装しながらクラスタリング手法について学ぶ。



## 2. データセットの説明
データ分析のプラットフォームであるKaggle上の[ワインのデータセット](https://www.kaggle.com/datasets/yasserh/wine-quality-dataset)についてKmeans法を利用した分析を行った. 
ワインデータセットは、11個の化学特性と品質スコアの特徴量から構成される。各特徴量の説明を以下に示す。

1. **fixed acidity (固定酸)**: ワインに含まれる酸の中で揮発しない酸。主に酒石酸やリンゴ酸が含まれる。単位: g/dm³
2. **volatile acidity (揮発酸)**: ワイン中の揮発性の酸。主に酢酸が含まれ、ワインの香りや味に影響を与える。単位: g/dm³
3. **citric acid (クエン酸)**: ワインの酸味とフレッシュさを強調するために使用される酸。単位: g/dm³
4. **residual sugar (残留糖)**: 発酵後に残る糖分。甘さの程度を示し、ワインのスタイルに影響する。単位: g/dm³
5. **chlorides (塩化物)**: ワインに含まれる塩分の量。ワインの塩味やミネラル感を強調する。単位: g/dm³
6. **free sulfur dioxide (遊離亜硫酸)**: ワイン中で直接利用可能な亜硫酸塩。酸化防止剤および抗菌剤として作用する。単位: mg/dm³
7. **total sulfur dioxide (全亜硫酸)**: ワインに含まれる全ての亜硫酸塩の量。遊離亜硫酸と結合亜硫酸の合計である。単位: mg/dm³
8. **density (密度)**: ワインの密度。アルコールや残留糖の濃度に影響を受ける。単位: g/cm³
9. **pH**: ワインの酸度を示す指標。pHの値が低いほど酸性が強い。
10. **sulphates (硫酸塩)**: ワインの保存と鮮度を保つために使用される成分。酸化防止に役立つ。単位: g/dm³
11. **alcohol (アルコール)**: ワインに含まれるアルコールの濃度。味わいや保存性に影響する。単位: %
12. **quality (品質スコア)**: 味覚テストによって評価されたワインの品質スコア。スコアは通常0〜10の範囲で、スコアが高いほど品質が良いとされる。



## 3. 分析手法の説明
本分析では、以下の手法を使用した、またソースコードは当レポジトリ内に示した：

- **主成分分析 (PCA)**: 高次元データを2次元に削減し、データの視覚化を容易にする。
- **K-Meansクラスタリング**: データを3つのクラスタに分類し、分析する。

### 手法の選んだ理由
- PCAは、低次元データによく用いられるペアプロットを今回の11次元データに利用した場合特徴をつかみづらかったため、高次元なデータセットにおいてもデータを視覚的に解釈しやすくするために使用した。
- K-Meansクラスタリングは、数値データの自然なグループを特定するのに効率のよい手法であるため使用した.



## 3. 分析結果の提示、考察

###　クラスタリング結果の確認
- KMeans法によってデータセットを3つにクラスタリングした. 
- PCAによって、元の高次元データの分散を最もよく説明する第1主成分とそれに直行する第2主成分を得た.
- それぞれの成分の値を座標としてクラスタリング結果を表した散布図を示す.

![image](https://github.com/user-attachments/assets/314c48ae-78ee-4866-bb8b-d3d2ebef9b65)

- クラスタリングが3つに適切に行われていることが確認できる.


### クラスタごとの特徴量のグラフ

- **fixed acidity (固定酸)**: g/dm³
![image](https://github.com/user-attachments/assets/4412a834-5cc5-4cc8-93e5-0af963c1dc5a)
 
- **volatile acidity (揮発酸)**: g/dm³
![image](https://github.com/user-attachments/assets/316f8be1-e3cc-46f0-93e6-513f5e67321a)

- **citric acid (クエン酸)**: g/dm³
![image](https://github.com/user-attachments/assets/f91c7b54-12a7-400f-87c1-7b2ddbabc865)

- **residual sugar (残留糖)**: g/dm³
![image](https://github.com/user-attachments/assets/ae176771-e771-48c8-b180-c274b89977fc)

- **chlorides (塩化物)**: g/dm³
![image](https://github.com/user-attachments/assets/03f8dd93-5629-4140-8371-c7036770a22b)
  
- **free sulfur dioxide (遊離亜硫酸)**: mg/dm³
![image](https://github.com/user-attachments/assets/0beaf917-3727-4344-af9c-a08bb790e598)

  
- **total sulfur dioxide (全亜硫酸)**: mg/dm³
![image](https://github.com/user-attachments/assets/4bc0efba-2157-4888-9771-11011675e53c)

- **density (密度)**: g/cm³
![image](https://github.com/user-attachments/assets/4eaff012-6d86-4146-9b58-efadf5b8e8b2)

- **pH**
![image](https://github.com/user-attachments/assets/7220a6fd-d940-4cb8-87af-a7b583a0379f)

- **sulphates (硫酸塩)**: g/dm³
![image](https://github.com/user-attachments/assets/fc3a7cf7-734e-4ce1-ab7a-a5d7d77c126f)

- **alcohol (アルコール)**: %
![image](https://github.com/user-attachments/assets/5cbda4db-28a0-4739-aa9e-aec030cde9c3)

- **quality (品質スコア)**: 0〜10
![image](https://github.com/user-attachments/assets/40b6a536-c733-4bca-9555-cceed8f396ba)


### クラスタごとの特徴量の平均値

- クラスタごとの各平均値を示す、


| cluster | fixed acidity | volatile acidity | citric acid | residual sugar | chlorides | free sulfur dioxide | total sulfur dioxide | density  | pH       | sulphates | alcohol  | quality |
|---------|---------------|------------------|-------------|----------------|-----------|---------------------|----------------------|----------|----------|-----------|----------|---------|
| 0       | 7.584328      | 0.536629         | 0.231617    | 2.441418       | 0.082463  | 16.728856           | 43.570896            | 0.995749 | 3.335746 | 0.644851  | 10.709287| 5.703980|
| 1       | 8.623784      | 0.523162         | 0.267595    | 2.534054       | 0.087224  | 15.143243           | 44.562162            | 0.997053 | 3.304757 | 0.630378  | 10.422432| 5.627027|
| 2       | 8.786792      | 0.533760         | 0.308949    | 2.628571       | 0.091485  | 14.880054           | 49.803235            | 0.997473 | 3.290458 | 0.698895  | 10.172237| 5.636119|


### 分析結果の考察
####クラスタ0:

- アルコール度数、遊離亜硫酸が高く、全亜硫酸が低い。品質スコアが最も高い。
- 高品質のワインはクラスタ0の特性（高アルコール度数、少し高めなpH, 低い遊離亜）を持つと考えられる。

#### クラスタ1:

- 固定酸が高い一方で、揮発性酸度が低めである。全体的にクラスタの中では2番目の大きさの値が多い中でqualityが低いのはこのバランスが品質に影響を与えていると考えられる。

#### クラスタ2:

- 保存性を高める硫酸塩を多く使用しながらも, qualityが中程度に保たれている. クラスタ2は保存性も高く、中品質を保つワインの特性と考えられる



## 4. 感想

多くのデータや次元があるにもかかわらず、 自分の想像以上にkmeans法で自然にグループ分けを行えた。 しかし、そこで得られた結果からクラスタの特性を考えるのも難しい問題であると感じた。



