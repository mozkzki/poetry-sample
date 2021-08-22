# Poetry

## 参考

- [【Python】Poetry始めてみた & Pipenv から poetry へ移行した所感 - Qiita](https://qiita.com/ragnar1904/items/0e5b8382757ccad9a56c)
- [Windows 10 で Python のインストールから Poetry と pyenv の利用 - Qiita](https://qiita.com/kerobot/items/3f4064d5174676080585)

## 各種コマンド

Poetry自体の導入 (Mac, Linux)

```bash
> curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python
```

Poetry自体の導入 (Windows) ※Powershell

```Powershll
> (Invoke-WebRequest -Uri https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py -UseBasicParsing).Content | python
```

バージョン確認

```sh
> poetry --version
> poetry -V
```

Poetry自体の更新

```sh
> poetry self update
```

設定の確認

```sh
> poetry config --list
```

設定 (例: プロジェクト内に virtualenv の仮想環境が作成されるようにする)

```sh
> poetry config virtualenvs.in-project true
```

プロジェクト新規作成 (project01ディレクトリ以下に各種ファイル生成)

```sh
> poetry new project01
> cd project01
> tree .

├── README.rst
├── project01
│   └── __init__.py
├── pyproject.toml
└── tests
    ├── __init__.py
    └── test_project01.py
```

パッケージ追加

```sh
> poetry add tqdm==4.48.2
```

バージョン指定方法

- [依存関係仕様 - Poetry documentation (ver. 1.1.6 日本語訳)](https://cocoatomo.github.io/poetry-ja/dependency-specification/)

パッケージ削除

```sh
> poetry remove tqdm
```

`pyproject.toml`のパッケージを一括インストール

```sh
> poetry install
```

`pyproject.toml`のパッケージを一括更新

```sh
> poetry update
```

スクリプト実行

```sh
> poetry run start
```

スクリプトサンプル

```toml
[tool.poetry.scripts]
start = "project01:main"
```

仮想環境に入る

```sh
> poetry shell
```

仮想環境から出る

```sh
> exit
もしくは
> deactivate
```
