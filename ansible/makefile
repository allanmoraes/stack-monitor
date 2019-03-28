deploy:
	ansible-playbook main.yml -i inventory \
		-t stack,telegraf \
		-e "docker_deploy=true" \
		-e "grafana_deploy=true" \
		-e "influx_deploy=true" -k

deploy-telegraf:
	ansible-playbook main.yml -i inventory \
		-t telegraf -k

deploy-docker:
	ansible-playbook main.yml -i inventory \
                -t stack \
                -e "docker_deploy=true" -k

deploy-grafana:
	ansible-playbook main.yml -i inventory \
                -t stack \
                -e "grafana_deploy=true" \
				-e "grafana_create_datasource=true" -k

deploy-grafana-no-datasource:
	ansible-playbook main.yml -i inventory \
                -t stack \
                -e "grafana_deploy=true" -k

deploy-influx:
	ansible-playbook main.yml -i inventory \
                -t stack \
                -e "influx_deploy=true" -k
