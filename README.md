#Passo a Passo Criação Projeto do Zero - Docker + Laravel + Nginx + Redis + PostgreSQL

##Obs: PC Windows já com Docker e Ubuntu instalado


1) Clonar este projeto dentro do seu Ubunto;

2) Alterar o nome das linhas container-name para o desejado de acordo com o projeto no arquivo docker-compose.yml

3) Comando para subir o Container inicial: docker compose up

4) Comando para instalar o Laravel dentro da pasta aplication: 
 - docker compose run --rm app composer create-project --prefer-dist laravel/laravel application

5) Atualizar as variaveis de ambiente no arquivo docker-compose.yml:
     - Pegar a App_Key do projeto gerada no arquivo .env
     - Abrir o docker-compose.yml e adicionar as seguintes linhas abaixo após o bloco *volume* do bloco app

    environment:
      - COMPOSER_HOME=/composer
      - COMPOSER_ALLOW_SUPERUSER=1
      - APP_ENV=local
      - APP_KEY=base64:fCMeCfu0vMMA34NbD6eqakNFSVsgHs8GGpuOBEVGeyk= //Alterar para a chave gerada no seu env

6) Derrubar os container antigos: docker compose down

7) Subir os container novamente com a nova configuração: docker compose up

8) Digitar o endereco: http://localhost:8000/

9) Agora o ambiente laravel irá funcionar corretamente com todos os componentes instalados nos containers Docker.
