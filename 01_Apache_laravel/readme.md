# 開発環境

## インストールするされるもの

- cloud9 ・・・Cloud9のダッシュボードからGIPを指定 ec2-userで接続することで利用可
- Docker
- git・・・Bitbucketに接続するための初期設定のみ ※1
- vscode・・・VS code経由でリモート接続した場合に`code`コマンド利用可能
- terraform・・・tfenvによって最新版をインストール
  - ※1
セットアップ後 `/home/ec2-user/.ssh/id_rsa` にbitbukcetに登録している秘密鍵を設定してあげる必要がある。
`.ssh/config`でHUB-SSHへの接続可（VPC　Peer）前提になっている。



## localhostで実行したい場合
gitに接続するためのユーザはデフォルトではテストユーザの値が入っているため明示的に指定する。

- DryRun
```shell
ansible-playbook main.yml -i localhost, -c local --extra-vars "user_name=\"テスト\"" --extra-vars "user_email=test@exmple.com"  -C
 ```

 sudo でパスワードが必要な環境で実行する場合はこっち
 ```shell
 ansible-playbook main.yml -i localhost, -c local -C --ask-become-pass
 ```


 - Apply
```shell
ansible-playbook main.yml -i localhost, -c local --extra-vars "user_name=\"テスト\"" --extra-vars "user_email=test@exmple.com" -C
 ```
