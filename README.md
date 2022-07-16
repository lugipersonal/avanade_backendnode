# Carfinder - API

## URL do Projeto:
[Clique aqui](https://carfinder-api.herokuapp.com/)

## Para acessar o swagger:
[Clique aqui](https://carfinder-api.herokuapp.com/swagger/)

## Collections Insomnia:
[Clique aqui](Insomnia_2022-07-04.yaml)

### Projeto exclusivo Icarros <> GamaAcademy

### Projeto exclusivo Avanade <> GamaAcademy

#### Publicando na Azure

Passo 1 - Criar um fork do projeto para domínio do mesmo, uso. <br>
Passo 2 - Provisionar recursos dentro do Azure (App Services) <br>
    - Devemos informar, resources group, nome da aplicação (o nome deve ser 
    único), informar run time, informar sistema operacional e selecionar o
    tamanho / configuração do hardware alocado. <br>
Passo 3 - Abrir o repositório com o projeto para edição do mesmo.
Passo 4 - Devemos criar as pastas para criar nossa pipeline
    Diretórios/arquivo (.github/workflows/prod.yml) <br>

##### Pipeline template:

'''
name: Pipeline CI/CD - Prod

on:
  push:
    branchs:
      - main
  workflow_dispatch:   

  jobs:
    build-and-deploy:
      name: Iniciando build e deploy
      runs-on: ubuntu-latest
      environment: production
      steps:
      - uses: actions/checkout@master
      - name: Configurando a versão do NodeJS
        uses: actions/setup-node@v1
        with:
          node-version: "16.x"
      - name: Estamos instalando dependências e compilando o projeto
        run: | 
          npm install
          npm run build --if-preset
      - name: Publicando na Azure
        uses: azure/webapps-deploy@v2  
        with:
          app-name: ${{ env.AZURE_WEBAPP_NAME }}
          publish-profile: ${{ secrets.AZURE_WEBAPP_PUBLISH_PROFILE }}
          package: .
'''

### Professor Douglas Morais
#### Desenvolvido com NodeJS | GamaAcademy