
# Andmesalvestus Ansible Projekt

See projekt on mõeldud andmeserverite seadistamiseks ja haldamiseks kasutades Ansible't.

## Projekti Struktuur

- **group_vars/**: Hoiab grupi taseme muutujaid. Määra siin väärtused, mida sa tahad reaalselt oma serveris kasutada. NB! Krüpteeri paroolid.
- **roles/**: Sisaldab erinevaid rolle, nagu näiteks `ceph`, `init`, `internet` jne.
- **ansible.cfg**: Ansible konfiguratsioonifail.
- **hosts**: Inventuurifail, mis määratleb serverid.
- **infra.yaml**: Playbook, mis kirjeldab, milliseid rolle ja ülesandeid täita.

## Näidis Inventuurifail (hosts)

```ini
[dataservers]
andmed1 ansible_host=192.168.161.111 netplan_ip=192.168.161.111
andmed2 ansible_host=192.168.161.112 netplan_ip=192.168.161.112
andmed3 ansible_host=192.168.161.113 netplan_ip=192.168.161.113

[all:vars]
ansible_ssh_user=andmed123
```
## Paigalda Ansible:

sudo apt update
sudo apt install ansible
ssh-keygen -t ed25519 -C "sinu.email@naide.ee"'

## Kopeeri SSH võtmed serveritesse:

ssh-copy-id andmed123@192.168.161.111
ssh-copy-id andmed123@192.168.161.112
ssh-copy-id andmed123@192.168.161.113

