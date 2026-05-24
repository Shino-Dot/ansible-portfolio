# Ansibleサーバー構築ポートフォリオ
AnsibleでWebアプリケーションの構築から監視環境までのセットアップを自動化したポートフォリオです。

## 構成図
Nginx (リバースプロキシ) → Gunicorn (アプリサーバー) → Django(Python) → PostgreSQL (DB)

## 監視構成
Prometheus → Loki → Grafana
Node Exporter → Prometheus (メトリクス収集)
Promtail → Loki (ログ収集)

## 使用技術
- Ansible
- Nginx / Apache / Gunicorn
- Django / PostgreSQL
- Prometheus / Grafana / Loki / Promtail
- CentOS Stream 9

## 環境
- 仮想マシン３台
- WSL2 (Ubuntu)

## 使い方
ansible-playbook -i inventory.ini site.yml

## 使用アプリケーション
- アプリ名: Albatross
- 作者: amamiya-lads
- リポジトリ: https://github.com/amamiya-labs/albatross


