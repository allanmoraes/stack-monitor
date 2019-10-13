Um conjunto de Playbooks do Ansible que configuram de forma automática uma stack de monitoramento.

---

## O que precisamos?
- Dois servidores Ubuntu com o Python instalado.

```bash
sudo apt install -y python
```

- Ansible na versão 2.5 ou superior e o comando make instalado em sua máquina local ou em um servidor onde executará o Ansible

```bash
sudo apt install -y ansible make
```

## Para rodar o Ansible
- Adicionar os IPs dos servidores no inventário em 
  - ansible/
    - production
  - ansible/group_vars/all/
    - docker.yml
      - docker_host
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
