# data-analysis-team-training


### 課題実施時の環境構築

- パターン１：　GoogleColaboratoryを使う場合 \
  ->　GitHubからプルし、該当の課題をダウンロード \
  ->　GoogleDriveに格納し、進める \
  ->　GitHubと連携して使うのでも可（やり方については確認中）


- パターン2:　DockerでJyupyterLabを使って行う \
  ->　GitHubにあるDockerfileを使う（自分で作っても良い） \
  ->　Dockerfileをbuild、 runする（ホストとコンテナのファイルシステムのマウントを忘れないように） \
  ->　localhost:8888　にアクセスし、JupyterLabに入り進める


### Dockerコンテナのbuild, runまで（参考）
1.  Dockerfileのあるディレクトリで、``` $docker build . ```
2.  ``` $ docker run -p 8888:8888 -v {host volume}:/work --name {コンテナ名} {イメージID} ```
3.  localhost:8888　にアクセスし確認

<注> 
- M1 Macの場合は、ビルドの際に、``` $docker build --platform linux/amd64 . ```とすること
- host volumeはDockerfileがあるパス（リポジトリをクローンして保存したパス）を指定すること
- また、8888ポートを使用している場合、別ポートを使うこと（例として、8889:8888とするなど）


### 課題の進めかた

- GoogleColaboratoryを使う場合 \
  -> GitHubから課題のフォルダをコピーし、GoogleDriveに格納する。課題のフォルダで新しいノートブックを作成し作業　\
  -> ファイル名は、[課題ファイル名]_[作成者名]_[年月日].ipynb （例：　Summarize_ishikawa_220328.ipynb）　\
  -> 各担当案件の研修ディレクトリに、作成したノートブックを格納すること

- Docker環境でGitLabを使う場合 \
  -> Gitで新しいブランチを切ること。ブランチ名は、[課題名]_[担当者]とする。　（例：　Summarize_ishikawa）　\
  -> GitLabを起動し、/workフォルダに課題のフォルダがあることを確認する。　\
  -> 課題のフォルダ内で、新しいノートブックを作成し、作業すること。　\
  -> ファイル名は、[課題ファイル名]_[作成者名]_[年月日].ipynb （例：　Summarize_ishikawa_220328.ipynb）　\
  -> 課題が完了したらプッシュし、プルリクエストを作成すること。


### 課題一覧（2022/6/15 時点）

- Python基本
  - 研修テスト_1.ipynb
  - 研修テスト_2.ipynb
  - 研修テスト_3.ipynb

- Numpy
  - numpy_1.py（予定）
- Pandas
  - pandas_1.py（予定）
- Matplotlib & Seaborn
  - vizualize_1.py（予定）

- データ分析基礎編
  - Easy-1 \
    -> Summarize.ipynb (要約統計量を算出する)\
    -> Visualize.ipynb (データの分布を確認する)
  - Easy-2 \
    -> Correlation.ipynb (相関分析の実施)
  - Standard-1 \
    ->　LinearRegression_1.ipynb (簡単な線形回帰モデル(単回帰モデル)を試す) \
    ->　DummyVariable.ipynb　　（簡単な線形回帰モデル(重回帰モデル)を試す, ダミー変数について）
  - Standard-2 \
    データ加工編 (「データサイエンティスト協会スキル定義委員」の公開データを利用　）　\
      -> DataProcessing_1.ipynb \
      -> DataProcessing_2.ipynb \
      -> DataProcessing_3.ipynb \
  - Standard-3 \
    -> Visualize_2.ipynb（予定）
    -> Visualize_3.ipynb（予定）
- データ分析応用編
  - No.1（時系列データを扱う）　\
    -> TimeSeriesDataProcessing.ipynb

- 統計モデル＆機械学習編編
  - 線形回帰モデル \
    -> Linear_Regression_2.ipynb \
    -> Linear_Regression_3.ipynb
  - ロジスティック回帰 \
    ->　Logistic_Regression.ipynb（予定）
  - 決定木モデル（予定）\
    回帰　\
      -> LightGBM_regression.ipynb \
      -> xgboost.ipynb(予定)　\
    分類　\
      -> LightGBM_classification.ipynb
  - 主成分分析（PCA）\
    ->　PCA.ipynb(予定)
  - k近傍法（kNN）　\
    回帰分析 \
      -> knn_regression.ipynb \
    分類器 \
      -> knn_classification.ipynb(予定)
  - SVM(サポートベクターマシン)（予定）\
      SVM.ipynb（予定）
  - 部分最小二乗回帰（PLSR）　（予定）
