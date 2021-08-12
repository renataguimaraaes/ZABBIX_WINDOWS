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


### Itens Monitorados: 
Os itens a ser monitorados são contadores do perfmon. O modelo utilizado para monitoramento é o lógico (236).
A chave utilizada é a discoverdisks.discovery .
E abaixo segue os contadores a nível de performance que foram selecionados para o template.

#### Itens monitorados:
- Average Disk queue lengh/Escrita
- Average Disk queue lengh/Leitura
- Average Disk queue lenght
- Avg. Disk sec/Escrita
- Avg. Disk sec/Leitura
- Avg. Disk sec/Transfer
- Current Disk Queue Length (Req)
- Disk Bytes/sec
- Disk Free
- Disk Free (%)
- Disk Reads/sec
- Disk Time (%)
- Disk Time Read (%)
- Disk Time Write (%)
- Disk Total
- Disk Transfers/sec
- Disk Writes/sec
- Idle Time (%)

## No cliente que será monitorado

1. Faça o download da pasta do [`Zabbix.rar`](ZABBIX), faça a descompactação do arquivo e copie para o c:\ do Windows.
2. Criar e Iniciar o Serviço no Windows via powershell: 
#### 64bits: 
C:\Zabbix\bin\win64\zabbix_agentd.exe -i -c C:\Zabbix\conf\zabbix_agentd.win.conf
sc start "zabbix agent"
##### 32bits: 
C:\Zabbix\bin\win32\zabbix_agentd.exe -i -c C:\Zabbix\conf\zabbix_agentd.win.conf
sc start "zabbix agent"

3. Iniciar o Serviço
4. Depois de alguns minutos, validar se a coleta foi iniciada.

## OBS:
Com a execução do script dentro do Windows, independente de ser um disco apresentado diretamente ou como ponto de montagem, é possível monitorar índices de performance.
Em aplicações que possuem a necessidade de adição de uma quantidade de discos além da limitação do Windows (26 unidades impostas pelas letras de unidade) é utiizada o mapeamento de discos dentro de uma unidade, ou mais popularmente, pontos de montagem. E o template padrão do Zabbix não consegue validar esse tipo de unidade, sendo então o objetivo desse projeto.
Qualquer dúvida, sugestão, segue meu linkedIn [`renataaguimaraes`] 
