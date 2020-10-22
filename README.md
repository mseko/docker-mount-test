# Dockerからホストのディレクトリをマウントできることを確認するためのdocker-compose
以下はWindowsの場合を想定した手順になっています。  
その他の環境の方は適宜自分の環境に合わせて手順を読み替えてください。  

1. 勉強会当日に使用する作業用フォルダを作成します。
   ここでは「c:\work」を作成したとします。
2. 1.で作成したディレクトリに、添付ファイルを展開してください。
3. 以下のコマンドを実行してください。  
  実行した際に表示されるログに「Mount is successful.」という文字列が含まれていたら成功です。
```
$ cd C:\work\mounttest ※入力箇所
$ docker-compose up ※入力箇所
Creating network "mounttest_default" with the default driver
Pulling mounttest (ubuntu:18.04)...
18.04: Pulling from library/ubuntu
171857c49d0f: Pull complete
419640447d26: Pull complete
61e52f862619: Pull complete
Digest: sha256:646942475da61b4ce9cc5b3fadb42642ea90e5d0de46111458e100ff2c7031e6
Status: Downloaded newer image for ubuntu:18.04
Creating mounttest_mounttest_1 ... done
Attaching to mounttest_mounttest_1
mounttest_1  | Mount is successful. ※このように「Mount is successful.」が含まれるログが出力されたら成功
mounttest_mounttest_1 exited with code 0
$ docker-compose down  ※入力箇所
```
