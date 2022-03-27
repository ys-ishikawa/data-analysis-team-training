# data-analysis-team-training


### 課題実施時の環境構築

- パターン１：　GoogleColaboratoryを使う場合 \
  ->　GitHubからプルし、該当の課題をダウンロード \
  ->　GoogleDriveに格納し、進める
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
- host volumeはDockerfileがあるパス（リポジトリをクローンして保存したパス）を指定すること。\
- また、8888ポートを使用している場合、別ポートを使うこと（例として、8889:8888とするなど）


### 課題一覧（2022/3/27時点）
- 基礎編
  - Easy-1\
    -> Summarize.ipynb (要約統計量を算出する)\
    -> Visualize.ipynb (データの分布を確認する)
  - Easy-2\
    -> Correlation.ipynb (相関分析の実施)\
  - Standard-1\
    ->　LinearRegression_1.ipynb (簡単な線形回帰モデル(単回帰モデル)を試す)
- 応用編
  - （作成中）
