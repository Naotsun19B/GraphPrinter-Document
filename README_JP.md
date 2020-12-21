# GraphPrinter

![title](https://user-images.githubusercontent.com/51815450/101246117-93b7aa00-3754-11eb-811c-da38fbbd5b64.PNG)

## 概要

このプラグインはUnreal Engineのグラフエディタ(BlueprintやMaterialなど...)を画像ファイルに出力するショートカットキーを追加します。
また、下の画像の様にグラフエディタで表示していない部分も含めて画像ファイルに出力できます。

#### エディタ上での状態
![grapheditor](https://user-images.githubusercontent.com/51815450/101246223-50117000-3755-11eb-8966-5da5124d420e.PNG)

#### 出力された画像
![BP_Sky_Sphere-RefreshMaterial](https://user-images.githubusercontent.com/51815450/101246304-cd3ce500-3755-11eb-8c59-14a8158f73c5.png)

## 動作環境

対象バージョン : UE4.21 ～ 4.26  
対象プラットフォーム : Windows, Mac, Linux 

## インストール

プロジェクトのPluginsフォルダにPlugins/GraphPrinterフォルダを入れてください。

## 使い方

追加される機能と対応するデフォルトのショートカットキーは以下の通りです。

|**ショートカットキー**|**機能**|
|:---:|---|
|Ctrl + F9|現在開いているグラフエディタのすべてのノードを含む画像を出力します。|
|Ctrl + F10|現在開いているグラフエディタの選択中のノードを含む画像を出力します。|
|Ctrl + F12|エディタの環境設定で設定されている出力先のディレクトリを開きます。|

また、ショートカットキーはエディタの環境設定のキーボードショートカットから変更できます。

![keyconfig](https://user-images.githubusercontent.com/51815450/101246571-8b14a300-3757-11eb-992b-d803d5b01cf9.PNG)

## オプション

![settings](https://user-images.githubusercontent.com/51815450/101246626-e5156880-3757-11eb-8cc6-b017afa3a331.PNG)

エディタの環境設定から設定できる項目は以下の通りです。

|**項目**|**説明**|
|---|---|
|Format|出力する画像の形式を設定します。対応している画像フォーマットは*png*、*jpeg*、*bmp*、*exr*です。|
|Compression Quality|出力する画像の圧縮率を設定します。|
|Filtering Mode|出力する際に使用するテクスチャのフィルタリングモードを設定します。|
|Use Gamma|出力する画像にガンマ値を反映するかを設定します。*false*の場合、出力された画像がエディタで見るよりも暗くなる場合があります。|
|Padding|画像に出力する際の余白を設定します。ノードが見切れる際などに値を大きくしてください。|
|Can Overwrite File when Export|画像を出力する際に同名のファイルを上書きするかを設定します。*false*の場合、同名のファイルがあった際にはサフィックスに連番が付きます。|
|Output Directory Path|出力先のディレクトリを設定します。デフォルトでは"[Project]/Saved/GraphPrinter/"以下となっています。|

## ライセンス

[MITライセンス](https://ja.wikipedia.org/wiki/MIT_License)

## 作者

[Naotsun](https://twitter.com/Naotsun_UE)

## 履歴

- (2020/12/06) v1.0   
  プラグインを公開