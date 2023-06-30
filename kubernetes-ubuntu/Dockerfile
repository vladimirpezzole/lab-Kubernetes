FROM ubuntu:23.04

# Instalar dependências do Ansible
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    ssh

# Instalar Ansible
RUN apt-get install -y ansible


# Copiar o playbook do Ansible
COPY playbook.yml /playbook.yml

# Executar o playbook do Ansible
RUN ansible-playbook /playbook.yml

# Definir o diretório de trabalho
WORKDIR /app
