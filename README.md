# (Under development)
# Passos para iniciar o projeto.


## 1. Criando um ambiente virtual em Python

```
mkdir datapipeline
cd datapipeline
python3 -m venv .env
source .env/bin/activate
````

## 2. Criaremos uma variável de ambiente que aponta para a pasta onde o Airflow será instalado:

```
export AIRFLOW_HOME=$(pwd)/airflow
```

Lembre sempre de manter esta variável ativa, caso contrário o Airflow será criado na pasta raiz do usuário. Feito isso, instalaremos o Airflow em nosso ambiente, aqui estamos usando a versão 1.10.14:

```
pip install apache-airflow==1.10.14 --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-1.10.14/constraints-3.7.txt"
````

## 3. Após instalar Airflow, iniciaremos o banco de dados da ferramenta:

```
airflow initdb
````

## 4. E para iniciar o serviço Webserver, responsável pela interface da ferramenta, digitaremos:

```
airflow webserver
````

## 5. Acessaremos a interface do Airflow no navegador usando o link: http://localhost:8080.

## 6. E para iniciarmos o serviço Scheduler, responsável pelo agendamento de tarefas para execução, digitaremos:
Utilize um segundo terminal com seu virtual environment ativado e exporte novamente a variável de ambiente.

```
export AIRFLOW_HOME=$(pwd)/airflow
airflow scheduler
```

## 6. Usaremos uma API para extrair dados do twitter que está disponível neste (link)[https://github.com/twitterdev/Twitter-API-v2-sample-code/blob/2bd47d1ecfa31a1d71ed7902e5ac9c222d575331/Recent-Search/recent_search.py]
