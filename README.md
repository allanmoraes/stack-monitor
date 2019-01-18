# DevOpsDaysPOA 2019

## Como subir um monitoramento em menos de 5 minutos

[Slides](https://google.com)

---

## O que precisamos?
- Dois servidores Ubuntu com o Python instalado

```bash
apt install python
```
- Adivionar os nomes e IPs dos servidores em inventory.yml
- Trocar as senhas do Influx e Grafaa em group_vars

```bash
ansible-playbook main.yml -i inventory.yml -k
```
