# Nginx + PHP8.0 + laravel(composer 2.1)

## インストールするされるもの

- Nginx
- PHP 8.0
- Composer 2.1
- mysql 5.7(client)


## localhostで実行したい場合

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
でNginxのページが表示される。 `XXXXX`の部分はユニーク


## laravel

- laravel インストール
```sh
sudo chmod 777 /usr/share/nginx/html
cd /usr/share/nginx/html
composer create-project laravel/laravel laratest
```

- 権限変更（apachユーザで書き込みできるようにするため
```sh
sudo chown -R nginx:nginx /usr/share/nginx/html/laratest
```

https://XXXXXXXXX.vfs.cloud9.us-west-2.amazonaws.com/laratest/public
でLaravelのページが表示される。 `XXXXX`の部分はユニーク
