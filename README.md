# assets-academia-data-ai-spark
Materiais utilizados para as aulas de apache spark da academia de Data & AI

# Link Documentação Instalação SPARK via Google Colab
https://medium.com/@dipan.saha/pyspark-made-easy-day-2-execute-pyspark-on-google-colabs-f3e57da946a

# Passo a Passo instalação Spark no Google Colab

## Passo 1: Download do sparks e outros pacotes essenciais

Abra uma célula de código e cole:
```python
!apt-get update # Update apt-get repository.
!apt-get install openjdk-8-jdk-headless -qq > /dev/null # Install Java.
!wget -q http://archive.apache.org/dist/spark/spark-3.1.1/spark-3.1.1-bin-hadoop3.2.tgz # Download Apache Sparks.
!tar xf spark-3.1.1-bin-hadoop3.2.tgz # Unzip the tgz file.
!pip install -q findspark # Install findspark. Adds PySpark to the System path during runtime.
```

## Passo 2:
Configuração de variáveis de ambiente:

Abra uma célula de código e cole:

```python
import os
os.environ["JAVA_HOME"] = "/usr/lib/jvm/java-8-openjdk-amd64"
os.environ["SPARK_HOME"] = "/content/spark-3.1.1-bin-hadoop3.2"
```

## Passo 3:
Em outra Célula, import a biblioteca e execute o script abaixo
```python
import findspark
findspark.init()
```

## Passo 4:
Em outra célula
Crie a sessão do spark:

```python
from pyspark.sql import SparkSession
spark = SparkSession.builder.master("local[*]").getOrCreate()
```

## Passo 5:
Em outra célula, para validar escreva:

```python
spark.version
```

## Passo 6:
**LINK DOWNLOAD DATASETS:**
https://www.kaggle.com/datasets/bwandowando/rotten-tomatoesall-time-best-super-hero-movies?resource=download&select=user_reviews.csv

Realizar download dos datasets:

_critic_reviews.csv_
_movies.csv_
_user_reviews.csv_
