# [Linux] C Shell (csh) journalctl の使い方: システムログの表示

## 概要
`journalctl` コマンドは、システムジャーナルからログメッセージを表示するためのツールです。主に、システムの状態やサービスの動作を確認するために使用されます。

## 使用法
基本的な構文は以下の通りです。

```
journalctl [オプション] [引数]
```

## 一般的なオプション
- `-b` : 現在のブートセッションのログを表示します。
- `-f` : リアルタイムでログを追跡します。
- `--since` : 指定した日時以降のログを表示します。
- `--until` : 指定した日時までのログを表示します。
- `-u` : 特定のユニット（サービス）のログを表示します。

## 一般的な例
以下は、`journalctl` コマンドのいくつかの実用的な例です。

- 現在のブートセッションのログを表示する:
  ```bash
  journalctl -b
  ```

- リアルタイムでログを追跡する:
  ```bash
  journalctl -f
  ```

- 特定のサービスのログを表示する（例: sshd サービス）:
  ```bash
  journalctl -u sshd
  ```

- 指定した日時以降のログを表示する:
  ```bash
  journalctl --since "2023-10-01 10:00:00"
  ```

- 指定した日時までのログを表示する:
  ```bash
  journalctl --until "2023-10-01 12:00:00"
  ```

## ヒント
- ログが多すぎる場合は、`-n` オプションを使って表示する行数を制限できます。例えば、最新の10行を表示するには、`journalctl -n 10` とします。
- `--no-pager` オプションを使用すると、出力をページャーに送らずに直接表示できます。これにより、スクリプトでの利用が容易になります。
- ログを特定のファイルに出力するには、リダイレクトを使用します。例えば、`journalctl > log.txt` とすることで、ログを `log.txt` ファイルに保存できます。