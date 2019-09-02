# Laboratório Nifi > Elastic
Nesse repositório estarão dispostos os arquivos necessários para configuração do ambiente:

## Pré requisitos:
* Docker instalado
* Docker compose instalado
* Git instalado

## Ambiente do laboratório:
* ElasticSearch (versão 7.3.1 atualmente) - Onde serão inseridos os dados
* Kibana (versão 7.3.1 atualmente) - Onde serão dispostos os dashboards e faremos os ajustes do index.
* Nifi (Versão 1.9.2 atualmente) - Ferramenta de ETL que fará o flow básico dos dados

## Docker compose
É um arquivo yml que vem com as configurações necessárias para subirmos esses dados em Docker para iniciarmos os trabalhos. Maiores detalhes sobre o conteudo dele, basta ver o vídeo abaixo.

https://youtu.be/sKnrKFVlDQQ


## Como fazer a execução.
Com o docker e o docker-compose instalados (no meu caso num Linux) basta baixar esse conteudo via ```git clone``` e entrando na pasta baixada rodar o comando abaixo:

```
sudo docker-compose up -d
```

Não precisa passar o nome do arquivo pois ele considera que já está no diretório corrente e certifique-se disso, rs. O conteudo de cada uma das imagens será baixado o que pode demorar um pouco, mas estando tudo no ar basta acessar no navegador com ```http://localhost:portas_abaixo```:
* Nifi - porta 8080
* Elasticsearch - Porta 9200
* Kibana - Porta 5601
  
## Monitorando o start dos serviços:
Podemos acompanhar os logs de inicialização de cada serviço com o comando abaixo:
```
sudo docker-compose logs -f
```

Caso haja alguma duvida, consulte o material completo no post do medium no link abaixo:
