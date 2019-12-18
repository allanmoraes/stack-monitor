Um conjunto de Playbooks do Ansible que configuram de forma automática uma stack de monitoramento básico

[Slides](https://s3-sa-east-1.amazonaws.com/thedevconf/presentations/TDC2019POA/containers/HYT-5307_2019-11-30T050854_Docker%20e%20Ansible%20para%20automatizar%20o%20monitoramento.pdf)
---

## O que precisamos?
- Dois servidores Ubuntu com o Python instalado.

```bash
sudo apt install -y python python-apt
```

- Ansible na versão 2.7 ou superior e o comando make instalado.

```bash
sudo apt install -y ansible make
```

## Para rodar o Ansible
- Adicionar os IPs dos servidores no inventário em 
  - ansible/
    - production
- Trocar as senhas do InfluxDB e Grafana em:
  - ansible/group_vars/all/
    - influxdb.yml
      - influx_user_password
      - influx_address
    - grafana.yml
      - grafana_secutiry_admin_password
      - grafana_dashboard_uid
    - telegraf.yml
      - telegraf_pass
- Rodar o playbook:

```bash
$ cd ansible
$ make deploy
```

Para acessar o Grafana, basta digitar no navegador http://YOURIPADDRESS:3000/
