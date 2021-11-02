# ansible_playbooks

## Ansible検証用コンテナ作成

### キーペア作成

```sh
ssh-keygen -t ed25519 -f id_rsa
```

### Docker起動

- Build (DockerFileを更新したら実行する必要がある。)
```sh
docker-compose build
```

- Run
```sh
docker-compose up -d
```

- Login（Macで実行するとかなり時間かかる どうにかならんか。。）
```sh
ssh -i id_rsa ec2-user@localhost -p 2222
```

```sh
docker exec -it ansible_playbooks_ansible_amd64_1 bash
```
