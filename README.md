# Argus (Codinome PROFANUS)

* [Sinopse](#sinopse)
* [Pré-requisitos](#prereq)
* [Roles executadas](#roles)
* [Resultado Esperado](#retorno)
* [Comandos](#com)
* [Status](#stauts)
  * [Autor](#autor)
  * [Mantenedores](#mant)

## Sinopse <a name="sinopse"></a>
Solução consolidada de monitoração da infraestrutura. 

## Pré-requisitos <a name="prereq"></a>
Containers:<br />
Prometeus [https://hub.docker.com/r/prom/prometheus/]<br />
Alertmanager [https://hub.docker.com/r/prom/alertmanager/]<br />
Grafana [https://hub.docker.com/r/grafana/grafana/]<br />

## Roles Executadas  <a name="roles"></a>
Informar quais são as roles executadas neste projeto, bem como as variáveis que as compõem.

| Parametros | Opções | Comentários |
| ------ | ------ | ------ |
| variavel1 | Default: [ ] |Uma variavel que receb uma lista que tem a alguma funćão.|
| variavel2 (required)|| variavel obrigatória com outra funcão qualquer  |
| variavel3| Choices:<ul><li>yes (default)</li><li>no</li></ul> | Yes (padrão): faz uma coisa. No: faz outra coisa |


## Resultado Esperado <a name="retorno"></a>
Inclua aqui os resultados esperados do projeto e quais serão as configurações adicionadas/alteradas nos hosts.

| chave | valor | Descricão |
| ------ | ------ | ------ |
| variavel_retorno | "string" | Uma variável contendo uma string.|

## Comandos <a name="com"></a>
### Prometheus: <a name="prometheus">
docker run --rm -dt --net prometheus -h prometheus --name prometheus -v /usr/aplic/argus/prometheus:/etc/prometheus -p10.8.5.177:9090:9090 prom/prometheus

### Alertmanager: <a name="alertmanager">
docker run --rm -dt --net prometheus -h alertmanager --name alertmanager -v /usr/aplic/argus/alertmanager/alertmanager.yml:/etc/alertmanager/alertmanager.yml -p10.8.5.177:5001:5001 -p10.8.5.177:9093:9093 prom/alertmanager

### Grafana: <a name="grafanar">
docker run --rm -dt --net prometheus -h grafana --name grafana -v /usr/aplic/argus/grafana/etc:/etc/grafana -v /usr/aplic/argus/grafana/var/lib/grafana:/var/lib/grafana -v /usr/aplic/argus/grafana/usr/share/grafana:/usr/share/grafana -p10.8.5.177:3000:3000 grafana/grafana

## Status <a name="status"></a>
Em desenvolvimento
