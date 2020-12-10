アセンブラ カルタ トレーニング
==


## セットアップ

- Amazon Linux 2の例

```
$ cd $srcdir
$ sudo yum groupinstall -y "Development Tools"
$ sudo yum install -y perl-App-cpanminus.noarch postgresql-devel.x86_64 postgresql-server.x86_64
$ sudo cpanm Carton
$ carton
$ sudo -u postgres initdb -D /var/lib/pgsql/data
$ sudo systemctl start postgresql
$ sudo -u postgres psql << a
create user asm;
alter user asm with password 'asm';
create database asm with owner=asm;
a
$ psql -U asm < asm.sql
```

## 起動

```
% carton exec plackup -s Starlet
```
