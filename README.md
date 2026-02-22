# ml_practice
<<<<<<< HEAD
## Day1: GPU & virtual environment check


# Heart Disease Analysis

---
=======
<<<<<<< HEAD
## Day1: GPU環境確認・仮想環境確認
- GPU利用可: True
- GPU名: NVIDIA GeForce RTX4070
- 仮想環境: venv 作成済み
=======
## Day1: GPU & virtual environment check
>>>>>>> 3f1b7dc (Add Day1 record)
>>>>>>> 6f1b54a (docs: add Day4 summary)

## Day4: Heart Disease Dataset Analysis

- **Dataset**: Heart Disease (1025 rows, 14 columns, target: 0/1)
- **Purpose**: データ構造の確認と簡単な集計/可視化
- **Steps**:
  - pandas, numpyで読み込み,'df.info()' / 'df.describe()'で確認
  - 欠損地なし、ターゲット0/1はほぼ均等
  - 相関分析
    - 'target' に強く影響する特徴量: cp, thalach, slope
  - ヒートマップで視覚化
  - 箱ひげ図で特徴量とターゲットの関係を確認
- **Observations**:
  - cp(胸痛タイプ)やthalach(最大心拍数)がtarget=1に影響
  - 年齢や性別も少し傾向あり

## Day5: Logistic Regression

- **Purpose**: 予測モデルの構築と評価
- **Steps**:
  - 特徴量とターゲットを分ける
    '''python
    X = df.drop("target", axis=1)
    y = df["target"]
    '''
  - データを学習用80%、テスト用20%に分割
  - LogisticRegression(max_iter=1000)でモデル作成
  - 学習(fit) → 予測(predict) → 評価
- **Results**:
  - **Accuracy**: 0.80
  - **Precision / Recall / F1-score**:
    | class | precision | recall | f1-score |
    |-------|-----------|--------|----------|
    | 0     | 0.85      | 0.72   | 0.78     |
    | 1     | 0.76      | 0.87   | 0.81     |
  - **Feature Coefficients** (影響大きい順):
    | feature | coef |
    |---------|------|
    | cp      | 0.847 |
    | slope   | 0.536 |
    | restecg | 0.262 |
- **Obseravtions**:
  - cpやslopeはtarget=1に寄与
  - sex, thal, exangはtarget=0に寄与
  - 医療用とではrecallを重視