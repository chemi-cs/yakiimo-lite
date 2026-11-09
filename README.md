# 焼き芋から学ぶ Python：JupyterLite＋RDKit

中学生向けのPython教材を、GitHub Pagesからブラウザで開いて実行するための一式です。
生徒のPCにPythonをインストールする必要はありません。

**授業用サイト： [JupyterLiteを開く](https://chemi-cs.github.io/yakiimo-lite/lab/index.html)**  
開いたら、左のファイル一覧から `yakiimo_python_junior.ipynb` をダブルクリックしてください。

化学の発展パートでは、Python版RDKitを使って分子式・分子量・2D構造式・3D座標を求めます。
`from rdkit import Chem`や`AllChem.EmbedMolecule`を実行する構成です。RDKit.jsへの置き換えではありません。

## この一式の使い方

**ZIPを展開し、設定・教材・wheelをまとめてGitHubへ置いてください。**
`yakiimo_python_junior.ipynb`だけを一般のJupyterLiteサイトへアップロードしても、この実行環境にはなりません。

| 配置するファイル・フォルダー | 役割 |
| --- | --- |
| `.github/workflows/deploy.yml` | GitHub Actionsでサイトを作り、Pagesへ公開 |
| `jupyter-lite.json` | Pyodide 0.29.4とPythonカーネルの自動起動を設定 |
| `jupyter_lite_config.json` | 教材の場所とサイトの出力先を指定 |
| `requirements.txt` | サイトを作るためのJupyterLiteなどを指定 |
| `content/yakiimo_python_junior.ipynb` | 授業用Notebook |
| `content/1.2.png`、`content/5wqs.pdb` | 教材で使う画像・構造データ |
| `pypi/` | この環境用RDKitとpy3Dmolのwheel |
| `THIRD_PARTY_NOTICES.md` | 入手元・ライセンス・ファイルのSHA-256 |

## GitHub Pagesで公開する

1. ZIPをPC上で展開します。ZIPファイルそのものをアップロードするのではなく、中のファイルを使います。
2. GitHubにログインし、**New repository**で新しいリポジトリを作ります。名前の例は`yakiimo-lite`、公開範囲は**Public**です。**Add a README file**を有効にして作成すると、その後のアップロード画面を開きやすくなります。教材とリポジトリの内容は公開されます。
3. リポジトリの**Settings → Pages → Build and deployment → Source**を**GitHub Actions**にします。
4. **Code → Add file → Upload files**で、展開した一式をアップロードします。リポジトリの直下に`requirements.txt`や`content/`が来るように置き、外側のフォルダーをもう一段作らないでください。
5. **`.github`フォルダーも必ず含めます。** 隠しフォルダーが見えない場合は、エクスプローラーの隠しファイル表示などを有効にします。アップロード後、GitHub上に`.github/workflows/deploy.yml`があることを確認してください。
6. **Commit changes**で`main`ブランチへ保存します。**Actions**タブで`Build and deploy JupyterLite`が動きます。実行が無効になっている場合は有効にし、必要なら同じワークフローの**Run workflow**を実行します。
7. `build`と`deploy`が完了したら、**Settings → Pages → Visit site**から開きます。反映には数分かかることがあります。

リポジトリ名を`yakiimo-lite`にした場合の授業用URLは次の形です。`YOUR_GITHUB_USERNAME`を自分のGitHubユーザー名に置き換えます。

```text
https://YOUR_GITHUB_USERNAME.github.io/yakiimo-lite/lab/index.html
```

開いた画面のファイル一覧から、`yakiimo_python_junior.ipynb`をダブルクリックしてください。
生徒へはこのPagesのURLを配布します。生徒用のGitHubアカウントは必要ありません。

既存の`yakiimo`などのリポジトリにも、この一式をコピーできます。同名の設定や既存の公開用ワークフローがある場合は内容を確認して統合してください。このワークフローは`main`ブランチを対象にしています。

## 授業で実行する

- Notebookを開くと、`Python (Pyodide)`カーネルが自動で選択・起動します。初回は読み込みに時間がかかります。`Python (Pyodide)`の表示に切り替わったら、上から順にセルを実行します。通常は`Shift + Enter`で次へ進めます。
- 化学パートは、最初の準備セルを1回実行してから2D・3Dのセルへ進みます。初回の読み込みは時間がかかることがあります。
- 2D表示ではSVGを使います。同梱RDKitはCairoによるPNG描画に対応していないため、`Draw.MolToImage()`は使用できません。
- Pico用の温度制御コードは読む資料です。ブラウザから実機のヒーターを制御する機能はありません。
- 解答例はNotebook内にあります。自動採点・解答の回収・生徒同士の同期機能はありません。

生徒の編集は各ブラウザに保存され、GitHubへ自動送信されません。
授業の最後にはNotebookを右クリックして**Download**し、各自のPCへ保存してください。
共用PCのリセットやブラウザデータの削除により、ブラウザ内の編集内容は失われる場合があります。

## RDKitの環境について

この教材は、通常のPyPI版とは別に作られた**Pyodide向けの実験的なRDKit wheel**を同梱しています。
バージョン番号が同じでも、一般のPC用RDKit wheelとは異なります。

| 項目 | この一式の設定 |
| --- | --- |
| Pyodide | 0.29.4 |
| ブラウザ内Python | 3.13系 |
| RDKit | 2026.3.6、`cp313`・`pyemscripten_2025_0_wasm32`用 |
| py3Dmol | 2.5.2 |
| サイトのビルド | JupyterLite core／Pyodide kernel 0.8.7、JupyterLab 4.6.6 |

**`jupyter-lite.json`のPyodideを別バージョンへ変更しないでください。**
このwheelは上記のPython・WebAssembly環境に合わせたもので、Python 3.14などへそのまま移すことはできません。
ルートの`requirements.txt`へ`rdkit`を追記しても、ブラウザ内のRDKitがインストールされる仕組みではありません。

初回起動や必要なパッケージの読み込みにはインターネット接続が必要です。
Pyodideおよび3Dmol.jsは`cdn.jsdelivr.net`から読み込みます。必要に応じて外部パッケージ配布先への通信も発生します。
RDKitとpy3DmolのwheelはPagesサイトから読み込みます。この一式は完全オフライン用ではありません。

JupyterLiteをChromiumブラウザで開き、Notebookの全45コードセルをエラーなく実行しました。麦芽糖のSVG描画・3D表示を画面で確認し、麦芽糖と酵素の3Dビューアーが生成されることも確認しています。別途、Pyodide 0.29.4上で麦芽糖・エタノール・水の分子式・分子量・3D座標生成・UFFによる構造最適化を検証しました。
RDKitの全機能を網羅した検証ではありません。校内ネットワークや生徒の端末では未確認です。授業前に実際に使う端末・ネットワークで準備セルと2D・3D表示を確認してください。

## 更新とトラブル時の確認

- 教材を変更するときは、GitHubの`content/`内のファイルを更新して`main`へコミットします。再ビルドと公開が自動で始まります。
- ページが404になる場合は、PagesのSource、Actionsの結果、URL中のリポジトリ名を確認します。
- Actionsが動かない場合は、`.github/workflows/deploy.yml`の配置と`main`ブランチへのコミットを確認します。
- RDKitの読み込みに失敗する場合は、この一式から作ったPagesサイトを開いていることと、`pypi/`のwheelをアップロード済みであることを確認します。
- 更新した教材が見えない場合、ブラウザに保存された編集済みNotebookが優先されていることがあります。先に編集内容をDownloadしてから、別のブラウザプロファイルで公開版を確認します。

## ローカルでビルドする場合

これは講師・管理者向けの任意の手順です。生徒のPCで行う必要はありません。
Python 3.12の仮想環境などで、リポジトリ直下から実行します。

```bash
python -m pip install -r requirements.txt
jupyter lite build
python -m http.server 8000 --directory dist
```

`http://localhost:8000/lab/index.html`を開きます。HTMLファイルをダブルクリックする`file://`形式では起動しないでください。

元教材：[chemi-cs/yakiimo](https://github.com/chemi-cs/yakiimo)  
公式手順：[JupyterLiteをGitHub Pagesへ公開する](https://jupyterlite.readthedocs.io/en/stable/quickstart/deploy.html)
