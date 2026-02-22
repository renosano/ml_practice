# ml_practice
## Day1: GPU & virtual environment check


# Heart Disease Analysis

---

## Day4: 相関と可視化

### やったこと
- 相関行列の作成
- sns.heatmapで可視化
- 箱ひげ図で分布確認

### 分かったこと
- age と thalach の相関 = -0.39
- 若い人ほど最大心拍数が高い傾向
- target=1 は若め & thalach 高め

### 考察
thalach が効いているように見えるが、
age の影響を受けている可能性あり（交絡）。

単変量ではなく、多変量で検証が必要。

### 次にやること
- ロジスティック回帰で確認