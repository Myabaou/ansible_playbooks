# 開発環境

## インストールするされるもの

- terraform・・・tfenvによって最新版をインストール
  - ※1
セットアップ後 `/home/ec2-user/.ssh/id_rsa` にbitbukcetに登録している秘密鍵を設定してあげる必要がある。
`.ssh/config`でHUB-SSHへの接続可（VPC　Peer）前提になっている。

## localhostで実行したい場合
gitに接続するためのユーザはデフォルトではテストユーザの値が入っているため明示的に指定する。

- DryRun
```shell
ansible-playbook main.yml -i localhost, -c local -C
 ```

 sudo でパスワードが必要な環境で実行する場合はこっち
 ```shell
 ansible-playbook main.yml -i localhost, -c local -C --ask-become-pass
 ```




 - Apply
```shell
ansible-playbook main.yml -i localhost, -c local
 ```


---

## Cloud9上で実行した場合

https://5796f72561c649d1b341c8029378cfd9.vfs.cloud9.us-west-2.amazonaws.com/
でApacheのページが表示される。 XXXXX.vfs.cloud9 で`XXXXX`の部分はユニーク
