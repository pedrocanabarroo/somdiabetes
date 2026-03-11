# Usa uma imagem oficial leve do Python
FROM python:3.11-slim

# Define variáveis de ambiente para o Python não gerar arquivos .pyc 
# e para que o log apareça em tempo real no console
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Define o diretório de trabalho dentro do container
WORKDIR /somdiabetes

# Instala dependências do sistema (necessárias para o Postgres, por exemplo)
RUN apt-get update && apt-get install -y \
    libpq-dev \
    gcc \
    && rm -rf /var/lib/apt/lists/*

# Instala as dependências do Python
COPY requirements.txt /somdiabetes/
RUN pip install --no-cache-dir -r requirements.txt

# Copia o restante do código do projeto
COPY . /somdiabetes/