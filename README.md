# Ansibleサーバー構築ポートフォリオ


## 構成図
Nginx (リバースプロキシ) → Apache (アプリサーバー) → MariaDB (DB)

## 使用技術
- Ansible
- Nginx
- Apache
- MariaDB
- CentOS Stream 9

## 環境
- 仮想マシン３台
- WSL2 (Ubuntu)

## 使い方
ansible-playbook -i inventory.ini site.yml
