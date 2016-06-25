# vagrant_wp

Vagrant + Ansible でWordpressの開発環境となる仮想サーバを作ります。

nginx + php-fpm + mariaDB な環境を作ります。

## 作成される環境

- CentOS 7.1
- nginx 1.9.1
- PHP 7.0
- MariaDB 10.1
  - rootパスワード:未設定
- Wordpress latest-jp
  - DB: wordpress
  - DB user: wp_user
  - DB pssword: wp_pswd
- avahi
  - vagrant-wp.local でアクセスできます
- firewalld
  - 次のポート以外は閉じます
    - 22
    - 80
    - 443   

## 準備

次のものをインストールしてください。

- [Vagrant](https://www.vagrantup.com/downloads.html) 1.8以上
- [Oracle VM VirtualBox](https://www.virtualbox.org/wiki/Downloads) 5.0以上

### 起動

仮想サーバーを起動するには次のコマンドを実行します。

```bash
$ vagrant up
```
最初の起動はOSイメージのダウンロードと環境構築が走るので少し時間がかかります。

起動後は次のURLでWordpressにアクセスできます。

http://vagrant-wp.local/

管理画面には次のURLでアクセスできます。

http://vagrant-wp.local/wp-admin/

最初にアクセスするとサイトのWordpresのインストールページが表示されます。
必要な情報を入力してインストールしてください。

### 再起動

仮想サーバを再起動するには次のコマンドを実行します。

```
 > vagrant reload
```

### 停止

仮想サーバを停止するには次のコマンドを実行します。

```
 > vagrant halt
```

### 再構築

環境を作りなおすときには一度破棄(destroy)して、再度 vagarnt up を実行します。

```
 > vagrant destroy
 > vagrant up
```

### SSHでログイン

仮想サーバにSSHで接続する場合には次のコマンドを実行します。

```
 > vagrant ssh
```

上記コマンドは次のアカウント/パスワードでログインするのと同じです。

- アカウント： vagrant
- パスワード： vagrant

ちなみにサーバのアドレスは 192.168.33.120 です。
