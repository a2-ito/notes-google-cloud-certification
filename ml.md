# ml

## Google Cloud Components
- AutoML Tables
  - データサポート
  - 特徴エンジニアリング
  - モデルトレーニング
  - AutoML Tables か BigQuery ML かの選択
  - モデルの透明性 と Cloud Logging
- Cloud Composer
  - Apache Airflow のマネージドサービス
  - Python で記述する
  - DAG: 有向非巡回グラフを使用してワークフローを定義
- Kubeflow Pipelines
  - Kubeflowオープンソースプロジェクトの１つ
  - 機械学習ワークフローの構築とデプロイ用のプラットフォーム
- AI platform 
  - AI Platform Pipelines
- Vertex AI
  - 統合型MLOpsプラットフォーム
- Data Catalog
  - 知見をもたらすデータを検索する
  - 操作
    - アクセス可能なデータアセットを検索する
    - メタデータでアセットにタグ付けする
- AI Platform Data Labeling Service
  - 入力
    - ラベルをつける、代表的なデータサンプルを含むデータセット
    - データセット内の可能性があるすべてのラベルをリストするラベルセット
    - ラベル付けタスクでラベル付け担当者を導く一連の指示

## 用語
- SDG: Stochastic Gradient Dscent
  - 確率的勾配降下法
- Epochs
  - 一つの訓練データを何回繰り返して学習させるのか
  - 1 Epoch = データセット全体をニューラルネットワークに1回与えて処理を行うこと
- Verbose
  - using or containing too many words
- Z-score normalization
  - x_new = (x - x_mean)/x_std
  - 通常の正規化よりも外れ値に強い
- L1/L2 regularization 
  - 正則化
  - モデルの複雑さを抑制する仕組みを誤差関数に埋め込む
- TPU: Tensor Processing Unit
  - ワットあたりのIOPSをより高くするために意図的に計算精度を犠牲にした設計となっている
  - 一般にGPUより学習に必要な計算の速度は早い
- ROC: Receiver Operation Characteristic
  - 2値分類で使用されるパフォーマンス計測の可視化手法
  - 横軸が false positive 縦軸が true positive
  - ランキング全体に渡る正確さを満遍なく評価
- PR: Precision-Recall
  - TNの値が大きくなりやすい場合や、ネガティブケースが豊富な場合には、PR曲線が適している
  - ランキングが上位のサンプルの予測の正確さを重視
    - 虫眼鏡的な。
- AUC: Area Under the Curve
  - ROC曲線の面積を示す。これが大きければ大きいほど機械学習モデルの性能がよい。
- Confusion Matrix 混同行列
  - 二値分類の結果をまとめた表
- Accuracy 正解率
  - Accuracy = (TP+TN)/(TP+FP+FN+TN)
- Recall 再現率
  - 実際に出てきたものの割合
  - 見逃し(FN)が多いかどうかを判定
    - 本来は Positive なのに Negative と判定してしまった
  - Recall = TP/(TP+FN)
  - 例
    - FN 「光の速さ」が実際にわかる本の数
    - 90/(90 + 110) = 90/200 = 0.45
    - 10/(10 + 190) = 10/200 = 0.05
- Precision 適合率
  - 予測値全体における正解率
  - 誤検知(FP)が多いほど低くなる
    - 本来は Negative なのに Positive と判定してしまった
  - Precision = TP/(TP+FP)
  - 例
    - FP 「光の速さ」と検索してヒットしたが、光の速さがわかるものではない本
    - 90/(90 + 100) = 90/190 = 0.473
    - 10/(10 + 100) = 10/110 = 0.09
- Rolling Average ローリング平均
  - データ・セットの平均が継続的に更新され、その時点までのデータすべてが算入される。
- XGBoost
  - eXtreme Gradient Boosting
  - 勾配Boosting
  - アンサンブル学習と決定木を組み合わせた手法で、非常に高い汎化能力を誇る
- RNN: Reccurent Neural Network
  - 回帰型ニューラルネットワーク
  - 可変長データを入力データとする
  - 隠れ層の値を再び隠れ層に入力する
    - 時系列データの解析が可能
- CNN: Convolutional Neural Network
  - 畳み込みニューラルネットワーク
  - 手書き文字認識や音声認識といった課題に応用ができる
  - 畳み込み層で画像の局所的な特徴を抽出し、プーリング層で特徴をまとめ上げている（画像の抽象化）
- TensorRT
  - NVIDIA社がNVIDIA製GPU製品向けに提供しているディープラーニング推論を高速に実行するためのソフトウェア開発キット(SDK)
  - 推論時間が短時間になる
- LSTM: Long Short-Term Memory ネットワーク
  - 長・短期記憶
  - サイズ不明のタイムラグが与えられ重要なイベントに挟まれている時系列を分類、処理、予測する目的で経験から学習することに適している
- Differential privacy
  - 差分プライバシ
  - 個人データが識別されないようにしながら大規模なデータセットから学習できるようにするアプローチ
  - ノイズを加えることによって個人が特定されにくくすることで、プライバシーを保護する
- Federated learning
  - 連合学習
  - データを集約せずに分散した状態で機械学習を行う方法、2017年にGoogle社が提唱
  - 例：スマートフォンの端末側で機械学習を行い、改善後のデータだけサーバに送る
- Redaction
  - the action of changing, removing, or putting black marks over parts of an official document before it is published in order to keep information secret
  - 権限のないユーザへの機密データの公開を回避するために、データの表示内容を変更して伏字化を行う仕組み 
- 勾配降下法 Gradient descent
- Batch size
  - 2000サンプルのデータセットを500サンプルずつにバッチに分割する
    - バッチサイズ: 500
- NLP: Natural Language Processing
  - 自然言語処理
- K-fold cross validation
  - 学習用データをk分割してk回学習させる
- Integrated Gradients
  - モデルの予測間の関係をその特徴の観点から説明することを目指している
  - 機能の重要性の理解、データの偏りの特定、モデルのパフォーマンスのデバック等多くのユースケースがある
- PCA: Principal Component Analysis
  - 主成分分析
  - 相関ある特徴量から、互いに無相関の合成関数を作る手法
- k-means
  - k平均法、教師あり学習、クラスタリング
- Loss function 損失関数
  - 正解値と、モデルによって出力された予測値のズレの大きさを計算するための関数
  - 例
    - Categorical hinge
    - Binary cross-entropy
      - 正・負両方から学習できる
    - Categorical cross-entropy
      - 真値が正のときからしか損失が計上されない
    - Sparse categorical cross-entropy
      - 巨大なデータセットに有効
- learning rate
  - 学習率
  - 学習スピードの速さ　0.1前後から数値を小さくしていくのがよい
- DLP: Data Loss Prevention
  - 情報漏えい対策
- Feature Engineering
  - 特徴量エンジエアリング
  - ドメイン知識を使用して生データから特徴を抽出するプロセス
- Continuous Evaluation
  - モデルの予測とグラウンドトゥルースラベルを比較して、モデルの成果を継続的にフィードバックする
- Resnet: Residual Network
  - ニューラルネットワークのモデルの一つ
  - 勾配消失問題（レイヤを増やすと勾配が消失、学習が進まない問題）及びdegradation problem（劣化問題）を解決
  - DNNのレイヤ数が増えてもきちんと学習ができるようになった
- Binning ビニング
  - 特徴量エンジニアリング
  - 連続値の特徴量を離散化してカテゴリ変数に変換する
  - 線形モデルにおいて、表現力を高める効果が期待できる
- AI Explanations
  - 予測結果に最も強く影響を及ぼした画像内の部分を示す画像のオーバレイが返される
- 時系列データ解析手法
  - MA(移動平均)
    - 変動が細かすぎて全体の傾向を掴みづらい場合に、「移動平均」を用いることで変化をより滑らかにしてデータを俯瞰する手法
  - ARIMA
    - 自己回帰モデル(AR)、移動平均モデル(MA)、和分モデル(I)の3つを組み合わせたモデル
  - SARIMA
    - ARIMAに「季節的な周期パターン」を加えたモデル
- One-Hot encoding
  - カテゴリ変数をモデルに学習させられるように、数値に置き換えるための手法
  - 例
    - 雇用形態：公務員、自営業、民間企業従業員
    - というデータがあったとき、各カラムを追加し、0or1を入れる
- 勾配降下法
  - バッチ勾配降下法
    - パラメータの更新のたびに全ての訓練データで勾配を計算する
    - 訓練データの量が増加するにつれて計算を行うのが難しくなる
  - ミニバッチ勾配降下法
    - 訓練データの中からいくつかのデータを取り出し、そのデータで計算した勾配に基づいてパラメータを更新する手法
    - バッチ勾配降下法に比べると必要なメモリ量が少なく、外れ値の影響も受けにくい
  - 確率的勾配降下法
    - 訓練データの中から一つデータを取り出し、そのデータから計算した勾配を用いてパラメータを更新していく手法
    - 計算量が少なくて済むが、外れ値などの影響を受けやすくなるためパラメータの更新が安定しない
- Z-score
  - 分布の平均値からのずれを示す値。
  - 注目している標本値と分布の平均値の差を分布の標準偏差で割った値で定義される。
  - Z-scoreの絶対値が大きければ大きいほど、分布の平均値からのずれが大きいことを示している。
- Softmax
  - 任意の入力xに対し、0.0〜1.0の範囲で出力
  - 分類問題における出力層の活性化関数として用いられる
- MSE: Mean Squared Error
  - 平均二乗誤差
  - 各データに対して「予測値と正解値の差(=誤差)」の二乗値を計算し、その総和をデータ数で割った値(=平均値)を出力する関数




## BQML
- `AUTO_CLASS_WEIGHTS`
  - 分類モデルのときだけ有効なパラメータ。
  - 不均衡データを分類するときにいい感じに重み付けしてくれるらしい機能
- `BATCH_SIZE`
  - ミニバッチ勾配降下法というトレーニングデータをサブセットに分けて最適なパラメータを見つける手法が使われるが、そのときのサブセットのサイズを指定する。
- `DROPOUT`
  - 過学習防止のために、学習を進める際にノードを無視する確率を指定。
  - 0.5 or 0.1 が多いらしい。

## Tensorflow
- TFRecords
  - Protocol Buffersフォーマットでシリアライズされたデータを詰め込むことができる
  - 画像データなどのバイナリでも、シリアライズしてしまえば詰め込むことが可能
  - メリット
    - TFRecords形式のファイルを扱う機能が提供されている
    - 高速：直接画像データを読み込むよりも、TFRecords形式に変換したものを利用したほうが高速にデータを処理することができる
- `from_tensors`
  - 入力を結合して、単一の要素を持つデータセットを返す
  - `[[1,2], [3,4]]`
- `from_tensor_slices`
  - 入力テンソルの各行に個別の要素を持つデータセットを作成する
  - `[1,2], [3,4]`
- `batch_size`
- `MirroredStrategy`
  - 複数のGPU、TPUを使用して学習するためのAPI



## Crash Course

### Testing for Algorithmic Correctness
機械学習アルゴリズムの正しさを評価しなさい。そのやり方によって本当に正解に近づくか？を確認する。
- Train your model for a few iterations and verify that the loss decreases.
- Train your algorithm without regularization. If your model is complex enough, it will memorize the training data and your training loss will be close to 0.
- Test specific subcomputations of your algorithm. For example, you can test that a part of your RNN runs once per element of the input data.

### Downsampling and Upweighting
An effective way to handle imbalanced data is to downsample and upweight the majority class. Let's start by defining those two new terms:
- Downsampling (in this context) means training on a disproportionately low subset of the majority class examples.
- Upweighting means adding an example weight to the downsampled class equal to the factor by which you downsampled.
