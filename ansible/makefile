deploy:
	ansible-playbook site.yml -i production \
		-t stack,telegraf \
		-e "docker_deploy=true" \
		-e "influx_deploy=true" \
		-e "grafana_deploy=true" \
		-e "grafana_create_datasource=true" -k

deploy-telegraf:
	ansible-playbook site.yml -i production \
		-t telegraf -k

deploy-docker:
	ansible-playbook site.yml -i production \
                -t stack \
                -e "docker_deploy=true" -k

deploy-grafana:
	ansible-playbook site.yml -i production \
                -t stack \
                -e "grafana_deploy=true" \
		-e "grafana_create_datasource=true" -k

deploy-grafana-no-datasource:
	ansible-playbook site.yml -i production \
                -t stack \
                -e "grafana_deploy=true" -k

deploy-influx:
	ansible-playbook site.yml -i production \
                -t stack \
                -e "influx_deploy=true" -k
