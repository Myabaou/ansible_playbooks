# Apache2.4 + PHP7.4 + laravel(composer 2.1)

## インストールするされるもの

- Apache 2.4
- PHP 7.4
- Composer 2.1


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

https://XXXXXXXXX.vfs.cloud9.us-west-2.amazonaws.com/
でApacheのページが表示される。 `XXXXX`の部分はユニーク


## laravel

- laravel インストール
```sh
cd /var/www/html/
composer create-project laravel/laravel laratest
```

- 権限変更（apachユーザで書き込みできるようにするため
```sh
chown -R apache:apache /var/www/html/laratest
```

https://XXXXXXXXX.vfs.cloud9.us-west-2.amazonaws.com/laratest/public
でApacheのページが表示される。 `XXXXX`の部分はユニーク
