# PC-1 用 musicplayer

残念ながら、スタンドアローン版でしか動作しない。

- プログラム: [musicplayer.ptr](musicplayer.ptr)
- サンプル曲: [sakura.ptr](sakura.ptr)

をテープのディレクトリに入れる。Windows なら "(ユーザーのディレクトリ)\AppData\LocalLow\AutomaticComputer\PC-1 on Unity\Tapes\"

R0 を Initial load し、R0 で musicplayer.ptr を読み込み、続けて sakura.ptr を読み込む。

t でテンポ、o でオクターブを設定。音名は a, b, ..., g, シャープは l を付ける。
ただし、O1 の B から O3 の B くらいしか出ない。休符は p. 
長さは 1, 2, 4, 8 など、省略すると 4. 
付点は d, 終わりは z, 最後は jla. で解釈・演奏ルーチンを実行。

演奏データもプログラムの一部として R0 で読み込み、読み込み後周期・長さのデータに変換して演奏する形になっている。
さらに続けてテープを読み込んで演奏できる。
データをイニシャルオーダーで読み込んで次々に処理、という方法は当時よくあったようである。
