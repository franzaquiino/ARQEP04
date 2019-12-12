EP04 - Stream de Dados

1.Subir os containers

docker-compose up -d
2.Iniciar o servi�o de stream

docker-compose run processor bash
3.O processor possui m�todos para enviar informa��o para a stream utilizando valores randomicos que est� comentado no vendas.py

3.1.Realizar os seguintes comandos para Envio de informa��es para a stream:

faust -A venda send vendasA '{"produto":"LARANJA","qtd":"3","valor":"3.43"}'

faust -A venda send vendasA '{"produto":"MILHO","qtd":"2","valor":"2.40"}'
4.Endere�os para visualizar as informa��es da stream em rotas

4.1.Realiza a contagem de vendas em R$ do �ltimo 1 minuto (sliding)

localhost:6066/rs_1_min/valor_1min
4.2.rRealiza a Contagem de vendas em quantidade de cada 2 minutos (tumbling)

localhost:6066/qtd_2_min/qtd_2_min