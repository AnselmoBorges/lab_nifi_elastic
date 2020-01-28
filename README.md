# Laboratório Nifi > Elastic
Nesse repositório estarão dispostos os arquivos necessários para configuração do ambiente:

## Pré requisitos:
* Docker instalado
* Docker compose instalado
* Git instalado

## Instalando Pré-reqs
Para instalar todos os pré reqs citados acima rode os comandos abaixo:

```
sudo yum update -y
sudo yum install docker git -y
sudo curl -L "https://github.com/docker/compose/releases/download/1.25.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```
Com tudo instalado validamos o docker compose:

```
docker-compose -version
```

## Ambiente do laboratório:
* ElasticSearch (versão 7.5.2 atualmente) - Onde serão inseridos os dados
* Kibana (versão 7.5.2 atualmente) - Onde serão dispostos os dashboards e faremos os ajustes do index.
* Nifi (Versão 1.11 atualmente) - Ferramenta de ETL que fará o flow básico dos dados

## Docker compose
É um arquivo yml que vem com as configurações necessárias para subirmos esses dados em Docker para iniciarmos os trabalhos. Maiores detalhes sobre o conteudo dele, basta ver o vídeo abaixo.

[![](http://img.youtube.com/vi/sKnrKFVlDQQ/0.jpg)](http://www.youtube.com/watch?v=sKnrKFVlDQQ "Criação de ambiente do LAB")

Para baixar o repositorio com o compose digite o comando abaixo:
```
git clone https://github.com/AnselmoBorges/lab_nifi_elastic.git
```
Entre dentro do diretório baixado:
```
cd lab_nifi_elastic
```

## Realize o start do deamon do Docker:
Por padrão o Docker não vem iniciado, sendo assim rodamos os comandos abaixo para iniciar o Docker:
```
sudo service docker start
```

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
