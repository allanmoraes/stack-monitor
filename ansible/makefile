deploy:
	ansible-playbook site.yml -i production \
		-t stack,telegraf \
		-e "docker_deploy=true" \
		-e "influx_deploy=true" \
		-e "grafana_deploy=true" \
		-e "grafana_create_datasource=true"

deploy-telegraf:
	ansible-playbook site.yml -i production \
		-t telegraf

deploy-docker:
	ansible-playbook site.yml -i production \
                -t stack \
                -e "docker_deploy=true"

deploy-grafana:
	ansible-playbook site.yml -i production \
                -t stack \
                -e "grafana_deploy=true" \
		-e "grafana_create_datasource=true"

deploy-grafana-no-datasource:
	ansible-playbook site.yml -i production \
                -t stack \
                -e "grafana_deploy=true"

deploy-influx:
	ansible-playbook site.yml -i production \
                -t stack \
                -e "influx_deploy=true"
