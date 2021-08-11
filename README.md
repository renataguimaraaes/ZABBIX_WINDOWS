# ZABBIX_WINDOWS
Template e scripts de monitoramento de performance e pontos de montagem dentro do Sistema Operacional Windows
Realizei a criação dessa solução com o objetivo de monitorar performance dos discos contidos dentro do Sistema Operacional Windows e 
também monitorar os discos adicionados como ponto de montagem. A solução serve para ambos os casos.
Template foi utilizado na versão do Zabbix 5.0.2

## No servidor zabbix
1. Importe o template
   [`Template_Monitoring_Performance_Windows.xml`](Template_Monitoring_Performance_Windows.xml)
   para o Zabbix server (clique no link ao lado para download).
2. Adicione o template para o servidor
3. Verifique se os novos dados estão chegando.



## No cliente a ser monitorado

1. Import the [`Template_App_Apache_HTTP_Server_active.xml`](Template_App_Apache_HTTP_Server_active.xml)
   into your Zabbix server (click on the `Raw` button to download).
2. Add the template to your host (or stack template)
3. Check if new data arrives

