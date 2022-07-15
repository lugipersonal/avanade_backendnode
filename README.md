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
'''

### Professor Douglas Morais
#### Desenvolvido com NodeJS | GamaAcademy