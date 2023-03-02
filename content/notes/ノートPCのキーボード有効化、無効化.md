---
title: ノートPCのキーボード有効化、無効化
feed: show
---
まずコマンドプロンプトを管理者権限で実行する。

次に以下のコマンドを実行する。

ノートPCのキーボード
無効化
```bash
reg add HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\i8042prt /v Start /t REG_DWORD /d 4 /f
```

有効化  
```bash
reg add HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\i8042prt /v Start /t REG_DWORD /d 1 /f
```

最後に再起動を行う。

## 注意点
ノートPCのキーボードを無効化することは、自己責任で行ってください。

もし誤って無効化してしまった場合は、外部キーボードなどを接続して再び有効化する他、スクリーンキーボードという機能が最近のwindowsにはあるので、それによって回復させてください。