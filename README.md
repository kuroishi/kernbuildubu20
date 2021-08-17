
```
$ git clone https://github.com/torvalds/linux.git # ソースコードを取得
$ cd linux
$ git checkout バージョン # ビルドしたいバージョンにcheckout

$ mkdir ../build # out-of-treeビルド（ソースコードと生成物を分離したビルド）の為のディレクトリを作成
$ make olddefconfig O=../build # 既存のコンフィグをコピー＆ビルド用ディレクトリに必要なものを生成
$ cd ../build # 以降、ソースコードの変更を伴わない場合、基本的にはビルド用ディレクトリで作業
$ make localmodcinfig # 不要なモジュールを無効化
$ make menuconfig # 個別に機能の選択 

$ LOCALVERSION=-mybuild make -j8 # カーネル本体＆モジュールのビルド
$ sudo make modules_install # モジュールのインストール
$ sudo make install # カーネル本体のインストール(GRUBのエントリ生成もしてくれる）

$ sudo reboot # 再起動後、必要に応じてgrubでビルドしたカーネルを選択
```

Refereneces
===========
- https://qiita.com/progrunner/items/d2ab0a85b3881a4b7ed8
