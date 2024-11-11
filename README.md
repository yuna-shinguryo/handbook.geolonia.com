# Geolonia ハンドブック


## ハンドブックの開発

### macOS

まず Python をインストールしてください。

```
$ brew install python
```

リポジトリを `git clone` して、作業用ディレクトリ内に移動してください。

```
$ git clone https://github.com/geolonia/handbook.geolonia.com
$ cd handbook.geolonia.com
```

作業用ディレクトリ内にPythonの仮想環境を作ってください。

```
$ python3 -m venv .venv && source .venv/bin/activate
```

以上で仮想環境ができました。以下のコマンドを実行すると `python` コマンドのパスが `.venv` 内のパスに変わっていることを確認できます。

```
$ which python
$ which pip
```

必要なパッケージをインストールしてください。

```
$ pip install --upgrade pip
$ pip install -r requirments.txt
```

`mkdocs serve` コマンドを実行すると、`http://127.0.0.1:8000/` でローカル環境上のハンドブックにアクセスすることができます。

```
$ mkdocs serve
INFO    -  Building documentation...
INFO    -  Cleaning site directory
INFO    -  Documentation built in 0.15 seconds
INFO    -  [14:52:00] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO    -  [14:52:00] Serving on http://127.0.0.1:8000/
INFO    -  [14:52:01] Browser connected: http://127.0.0.1:8000/
```

後日作業を再開するには以下のような手順で再開することができます。

```
$ git pull
$ source .venv/bin/activate
$ pip install --upgrade pip && pip install -r requirments.txt
$ mkdocs serve
```

詳しくはハンドブック内の「ハンドブックの開発 （開発者向け）」を参照してください。

#### `direnv` を使って仮想環境の有効化を自動化する

※ 以下は、上述の初期設定が完了していることが前提です。

Homebrew を使って `direnv` をインストールしてください。

```
$ brew install direnv
```

作業ディレクトリ内で以下のコマンドを実行してください。

```
$ direnv allow
```

以上で、作業ディレクトリ内に移動するだけで仮想環境が有効になりますので今後の作業がシンプルになります。

```
$ git pull
$ pip install --upgrade pip && pip install -r requirments.txt
$ mkdocs serve
```
