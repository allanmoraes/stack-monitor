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
- Adicionar os IPs dos servidores em 
  - ansible/
    - inventory.yml
- Trocar as senhas do InfluxDB e Grafana em:
  - ansible/group_vars/all/
    - influxdb.yml
      - influx_user_password
      - influx_address
    - grafana.yml
      - grafana_secutiry_admin_password
    - telegraf.yml
      - telegraf_pass
- Rodar o playbook:

```bash
$ cd ansible
$ make deploy
```

Para acessar o Grafana, basta digitar no navegador http://YOURIPADDRESS:3000/
