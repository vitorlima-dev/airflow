
# Airflow

O Apache Airflow é uma plataforma de código aberto para desenvolver, agendar e monitorar fluxos de trabalho orientados a lotes. Para saber mais leia a [documentação](https://airflow.apache.org/docs/apache-airflow/stable/#what-is-airflow) .

### Instalação & Configuração

A implantação do Airflow é feita através de um arquivo **docker-compose.yml** 
que deve ser encontrado na raiz do projeto. 

### Pré-requisito:
- [Docker](https://docs.docker.com/get-docker/) 
- [Git](https://git-scm.com/downloads)

**1 -** Clone o repositório do projeto :
 
        git clone --recurse-submodules --remote-submodules https://github.com/vitorlima-dev/airflow.git

**2 -** Crie um arquivo **.env** no diretório raiz do projeto como o exemplo abaixo :

        # Airflow
        AIRFLOW_IMAGE_NAME=2.6.0
        AIRFLOW_UID=1000
        _AIRFLOW_WWW_USER_USERNAME=airflow
        _AIRFLOW_WWW_USER_PASSWORD=airflow

        # Postgres
        POSTGRES_DB=airflow
        POSTGRES_USER=airflow
        POSTGRES_PASSWORD=airflow    


**3 -** Se for a primeira vez que vai provisionar o ambiente do airflow use :

    docker-compose --env-file .env up airflow-init

**4 -** Finalmente inicie os serviços :

    docker-compose --env-file .env up

**5 -** Acesse o airflow-web em [localhost:8080](http://localhost:8080)

### Estrutura de diretórios do projeto

    airflow
    ├───airflow-setup               # configurações do airflow
    │   ├───logs                    
    │   └───plugins
    ├───dags
    │   ├───hook                    # hook global
    │   ├───operators               # operators global
    │   ├───scripts                 # scripts global
    |   |                           
    │   └───turinamy                # diretório do projeto: ( dag + dependências )
    │       └───skilled_operators   # dependências exemplo (opcional)
    |
    └───datalake                    # repositório para dados em seu estado bruto/natural 
        └───turinamy                # repositório do projeto exemplo "turinamy"
            └───dataset_2023-05-09



![Docker](https://img.shields.io/badge/Docker-21209C?style=for-the-badge&logo=docker&logoColor=white) 
![Python](https://img.shields.io/badge/Python-23120B?style=for-the-badge&logo=python&logoColor=F1F1F1)
![Airflow](https://img.shields.io/badge/Airflow-purple?style=for-the-badge&logo=Apache%20Airflow&logoColor=white)
