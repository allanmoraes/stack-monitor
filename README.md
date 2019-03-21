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
    - telegraf.yml
- Rodar o playbook:

```bash
ansible-playbook main.yml -i inventory.yml
```
### Configurando o Grafana
- Acessar http://localhost:3000/
- Na tela inicial do Grafana, clique em *Configuration > Data Sources > Add Data Source*
- Escolha a opção *InfluxDB*
- Você será redirecionado para a tela de confguração do *Data Source*
- Você deve fornecer:
  - Settings
    - Name: Nome para identificação
  - HTTP
    - URL: Endereço do InfluxDB
    - Access: Server (Default)
  - Auth
    - With Credentials
  - InfluxDB Details
    - Database: telegraf
    - User: telegraf
    - Password: ********
- Clique em *Save & Test*. Se a mensagem *Data source is working* aparecer a configuração está correta.
