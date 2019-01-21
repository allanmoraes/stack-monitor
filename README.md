# DevOpsDaysPOA 2019

## Automatizando o Monitoramento de Infraestrutura

[Slides](https://google.com)

---

## O que precisamos?
- Dois servidores Ubuntu com o Python instalado.

```bash
sudo apt install -y python
```

- Ansible na versão 2.5 ou superior, instalado em sua máquina local ou em um servidor

```bash
sudo apt install -y ansible
```

## Para rodar o Ansible
- Adicionar os nomes e IPs dos servidores em 
  - ansible/
    - inventory.yml
- Trocar as senhas do InfluxDB e Grafana em:
  - ansible/group_vars/all/
    - influxdb.yml
    - grafana.yml
- Para rodar o playbook:

```bash
ansible-playbook main.yml -i inventory.yml -k
```
