### fcalcとは
fcalcは分数計算のできる電卓です。
1行入力し、その計算結果を表示します。
fcalcはスクリプト言語Luaで書かれています。
fcalcはlinuxで動きますが、Luaをインストールしてwindowsでも動くと思われます。
fcalcはDebianでの動作確認をしています。

### fcalcのインストール
fcalcそのもの以外に、lua, LuaRocks, readline.lua, fraction.luaが必要です。

- [lua](http://www.lua.org/download.html)をダウンロードし、インストールしてください。バージョン5.3.2は動作確認済みです
- [LuaRocks](https://github.com/keplerproject/luarocks/wiki/Download)をダウンロードし、インストールしてください。
これは、readlineをインストールするためのパッケージマネージャです
- [readline.lua](http://www.pjb.com.au/comp/lua/readline.html)をLuaRocksを使ってインストールしてください。
なお、このプログラムにはGNU readlineが必要です（readline.luaのページを参照してください）
- [freaction.lua](https://github.com/ToshioCP/fraction.lua)をダウンロードし、インストールしてください
- fcalcをダウンロードしてください。このプログラムは、/usr/local/binに置き、実行可能属性を与えてください

### fcalcの使い方
fcalcは端末上で動作します。

- 端末を起動します
- コマンドラインから、「fcalc」と入力しEnterを押すと、「fcalc > 」というプロンプトが表示されます
- 計算したい式を入力します。整数と符号、加減乗除ができます。小数は使えません。四則以外の計算（累乗など）はできません。
- 入力行は編集ができます。バックスペースその他が機能します
- 入力時、ヒストリ機能が使えます。前回入力行が矢印キー「↑」で現れます。この機能はGNU readlineによるものです
- 結果が分数で表示されます。
- 空行を入力すると、終了します

### fcalcのカスタマイズ
fcalcはLua言語で書かれたスクリプトですので、書き換え可能です。
例えばヒストリ機能で使われる、ヒストリ保存ファイル名を変えることができます。
8行目の「~/.fraction_calculator_history」を変更してください。

- fcalcは主に入力行の字句解析と構文解析をしています
- 分数計算の実行は「fraction.lua」に任せています
- したがって、累乗などの計算をfcalcに導入したい場合は、fraction.luaとfcalcの両方を書き換えることが望ましい方法です
- fcalcのプログラムの解説が[Luaノート](https://floating-shore-5277.herokuapp.com/sections/53)にあります
