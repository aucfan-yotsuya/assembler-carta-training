アセンブラ カルタ トレーニング
==


## セットアップ

- Amazon Linux 2の例

```
% sudo yum groupinstall -y "Deevelopment Tools"
% sudo yum install -y perl-App-cpanminus.noarch postgresql-devel.x86_64 postgresql-server.x86_64
% sudo cpanm Carton
% carton
% sudo -u postgres psql << a
create user asm;
alter user asm with password 'asm';
create database asm with owner=asm;
a
% psql -U asm < asm.sql
```

## 起動

```
% plackup
```
