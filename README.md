# Oracle 11g XE install Vagrant és Puppet segítségével

forrás:
http://www.andrejkoelewijn.com/wp/2012/02/28/oracle-xe-on-ubuntu-using-vagrant-and-puppet/

## Lépések

Vagrant install

`gem install vagrant`

Ubuntu 11.10-es box letöltése

`vagrant box add ubuntu-1110-server-amd64
http://timhuegdon.com/vagrant-boxes/ubuntu-11.10.box`

Oracle telepítő RPM letöltése, majd átmásolása a
modules/oracle/files mappába (nincs bent git-ben)

VM létrehozása és oracle installálás. A debug log nélkül nekem nem
ment. A folyamat eltart néhány percig, és a végén kiír egy hibát is
(nem létezik a puppet group), de ennek ellenére működik a cucc.
 
`VAGRANT_LOG=DEBUG vagrant up`

## Leállítás / újraindítás

`vagrant suspend` : elaltatja a VM-et

`vagrant resume` : felébreszti a VM-et

`vagrant halt` : leállítja a VM-et

`vagrant up` : elindítja a VM-et

`vagrant up --no-provision` : szintén elindítja provisioning nélkül. A
provisioning az a folyamat, amikor a puppet felinstallálja a
szoftvereket. Ez csak az első futtatáskor szükséges jelen esetben.
