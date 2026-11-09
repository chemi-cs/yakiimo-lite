# Third-party notices

この配布物には、授業用Notebook、JupyterLiteの公開設定、および以下の第三者ソフトウェアのwheelを含みます。
各ソフトウェアにはそれぞれのライセンスが適用されます。wheel内のライセンス・著作権表示は変更せず保持しています。
この文書は、教材や画像を含む配布物全体に一つのライセンスを付与するものではありません。

## 同梱RDKit wheelの来歴

- ファイル：`rdkit-2026.3.6-cp313-cp313-pyemscripten_2025_0_wasm32.whl`
- RDKitバージョン：2026.3.6
- 対象：CPython 3.13、WebAssembly、`pyemscripten_2025_0_wasm32`
- この教材での実行環境：Pyodide 0.29.4
- 取得したCI成果物：[cp313-pyodide_wasm32-0.zip](https://nightly.link/fxcoudert/rdkit-pypi/actions/runs/34453672496/cp313-pyodide_wasm32-0.zip)
- CI実行：[fxcoudert/rdkit-pypi — run 34453672496](https://github.com/fxcoudert/rdkit-pypi/actions/runs/34453672496)
- 開発中の変更：[fxcoudert/rdkit-pypi pull request #2](https://github.com/fxcoudert/rdkit-pypi/pull/2)
- RDKit本体のソース：[rdkit/rdkit](https://github.com/rdkit/rdkit)
- wheelのビルド元：[fxcoudert/rdkit-pypi](https://github.com/fxcoudert/rdkit-pypi)
- wheel作成プロジェクトの上流：[kuelumbus/rdkit-pypi](https://github.com/kuelumbus/rdkit-pypi)
- wheelのSHA-256：`502080ad307325b03a83d9d5d10ef5d44dfa4bb45d55fcab6fc3bc68246e38db`

これは通常のPyPIで配布されるPC用wheelとは異なる、Pyodide向けの実験的なCIビルドです。
同じバージョン番号でも互換性が同じとは限りません。上記CI成果物の保存期間とは独立して、本配布物の`pypi/`に取得済みwheelを同梱しています。
GitHub Pagesを再ビルドする際にCI成果物を再ダウンロードする必要はありません。

RDKit本体はBSD 3-Clause License、wheel作成プロジェクトはMIT Licenseです。
本体の`rdkit/license.txt`と、パッケージの`rdkit-2026.3.6.dist-info/LICENSE.md`を以下にそのまま掲載します。

## 同梱py3Dmol wheelの来歴

- ファイル：`py3dmol-2.5.2-py2.py3-none-any.whl`
- バージョン：2.5.2
- 配布元：[PyPI — py3Dmol 2.5.2](https://pypi.org/project/py3Dmol/2.5.2/)
- ソース：[3dmol/3Dmol.js](https://github.com/3dmol/3Dmol.js)内の`py3Dmol`
- 著者：David Koes
- ライセンス：MIT
- wheelのSHA-256：`b921940ff046cf7ca008a249cbd5debec561dcf337f1e5f3df7ac5d4a1954e8e`

py3Dmolは3D表示のために、[3Dmol.js 2.5.2](https://cdn.jsdelivr.net/npm/3dmol@2.5.2/build/3Dmol-min.js)をブラウザで読み込みます。
3Dmol.jsのプロジェクトとライセンスは[公式リポジトリ](https://github.com/3dmol/3Dmol.js)を参照してください。
同梱wheelの`py3dmol-2.5.2.dist-info/licenses/LICENSE.txt`を以下にそのまま掲載します。

## ビルド時・実行時に利用するプロジェクト

- [JupyterLite](https://github.com/jupyterlite/jupyterlite)：BSD 3-Clause License。サイト生成時に配布される静的ファイルとライセンス表示を使用します。
- [JupyterLite Pyodide kernel](https://github.com/jupyterlite/pyodide-kernel)：JupyterLite内でPythonを動かすカーネルです。
- [JupyterLab](https://github.com/jupyterlab/jupyterlab)：BSD 3-Clause License。Notebookの画面を構成します。
- [Pyodide 0.29.4](https://github.com/pyodide/pyodide/tree/0.29.4)：MPL-2.0。実行時に[配布CDN](https://cdn.jsdelivr.net/pyodide/v0.29.4/full/pyodide.js)から読み込みます。Python、NumPy、Pillowなどの同梱・追加パッケージには各プロジェクトのライセンスも適用されます。

`requirements.txt`はビルドに使う直接依存のバージョンを指定しています。
ブラウザ側のPyodideのバージョンは`jupyter-lite.json`に固定しています。

## 教材・データの出典

- 元教材：[chemi-cs/yakiimo](https://github.com/chemi-cs/yakiimo)
- β-アミラーゼの構造：[RCSB PDB 5WQS](https://www.rcsb.org/structure/5WQS)。元教材に含まれる`5wqs.pdb`を引き継いでいます。
- 麦芽糖の構造参照：[PubChem CID 439186](https://pubchem.ncbi.nlm.nih.gov/compound/439186)
- `1.2.png`は元教材に含まれる画像です。Notebook内の画像直下に元の出典表示を保持しています。

## 同梱ライセンス原文

### `rdkit/license.txt`

```text
BSD 3-Clause License

Copyright (c) 2006-2015, Rational Discovery LLC, Greg Landrum, and Julie Penzotti and others
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```

### `rdkit-2026.3.6.dist-info/LICENSE.md`

```text
MIT License

Copyright (c) 2022 Christopher Kuenneth

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### `rdkit/Data/Fonts/amadeus_font_license.txt`

```text
This font was found on the internet and did not come with a license. While we try to make sure that all the fonts on fontsquirrel.com are properly licensed for commercial use, there are many fonts that have either been abandoned by their authors or the authors distribute their fonts without an explicit license. 

It is our opinion that if the unlicensed font is freely available for download from either the original source or from multiple free-font sites then we assume it to be safe to use the font commercially. This is no guarantee of such freedom, but there are so many unlicensed free fonts distributed by primary sources that the intentions must be read that the font is free to use how you like.

We are not lawyers and don't pretend to be them on TV. Please report any errors/violations you know of. http://www.fontsquirrel.com/contact
```

### `rdkit/Data/Fonts/roboto_regular_license.txt`

```text
The Roboto-Regular font is license with Apache 2.0.
https://www.apache.org/licenses/LICENSE-2.0
It was developed by Google for Android, apparently.
```

### `rdkit/Data/Fonts/telex_font_license.txt`

```text
Copyright 2011 The Telex Project Authors (info@andrestorresi.com.ar), with Reserved Font Name Telex.

This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is copied below, and is also available with a FAQ at: http://scripts.sil.org/OFL

-----------------------------------------------------------
SIL OPEN FONT LICENSE Version 1.1 - 26 February 2007
-----------------------------------------------------------

PREAMBLE
The goals of the Open Font License (OFL) are to stimulate worldwide development of collaborative font projects, to support the font creation efforts of academic and linguistic communities, and to provide a free and open framework in which fonts may be shared and improved in partnership with others.

The OFL allows the licensed fonts to be used, studied, modified and redistributed freely as long as they are not sold by themselves. The fonts, including any derivative works, can be bundled, embedded, redistributed and/or sold with any software provided that any reserved names are not used by derivative works. The fonts and derivatives, however, cannot be released under any other type of license. The requirement for fonts to remain under this license does not apply to any document created using the fonts or their derivatives.

DEFINITIONS
"Font Software" refers to the set of files released by the Copyright Holder(s) under this license and clearly marked as such. This may include source files, build scripts and documentation.

"Reserved Font Name" refers to any names specified as such after the copyright statement(s).

"Original Version" refers to the collection of Font Software components as distributed by the Copyright Holder(s).

"Modified Version" refers to any derivative made by adding to, deleting, or substituting -- in part or in whole -- any of the components of the Original Version, by changing formats or by porting the Font Software to a new environment.

"Author" refers to any designer, engineer, programmer, technical writer or other person who contributed to the Font Software.

PERMISSION & CONDITIONS
Permission is hereby granted, free of charge, to any person obtaining a copy of the Font Software, to use, study, copy, merge, embed, modify, redistribute, and sell modified and unmodified copies of the Font Software, subject to the following conditions:

1) Neither the Font Software nor any of its individual components, in Original or Modified Versions, may be sold by itself.

2) Original or Modified Versions of the Font Software may be bundled, redistributed and/or sold with any software, provided that each copy contains the above copyright notice and this license. These can be included either as stand-alone text files, human-readable headers or in the appropriate machine-readable metadata fields within text or binary files as long as those fields can be easily viewed by the user.

3) No Modified Version of the Font Software may use the Reserved Font Name(s) unless explicit written permission is granted by the corresponding Copyright Holder. This restriction only applies to the primary font name as presented to the users.

4) The name(s) of the Copyright Holder(s) or the Author(s) of the Font Software shall not be used to promote, endorse or advertise any Modified Version, except to acknowledge the contribution(s) of the Copyright Holder(s) and the Author(s) or with their explicit written permission.

5) The Font Software, modified or unmodified, in part or in whole, must be distributed entirely under this license, and must not be distributed under any other license. The requirement for fonts to remain under this license does not apply to any document created using the Font Software.

TERMINATION
This license becomes null and void if any of the above conditions are not met.

DISCLAIMER
THE FONT SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT OF COPYRIGHT, PATENT, TRADEMARK, OR OTHER RIGHT. IN NO EVENT SHALL THE COPYRIGHT HOLDER BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, INCLUDING ANY GENERAL, SPECIAL, INDIRECT, INCIDENTAL, OR CONSEQUENTIAL DAMAGES, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF THE USE OR INABILITY TO USE THE FONT SOFTWARE OR FROM OTHER DEALINGS IN THE FONT SOFTWARE.
```

### `py3dmol-2.5.2.dist-info/licenses/LICENSE.txt`

```text
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

