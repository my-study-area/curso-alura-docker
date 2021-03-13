# curso-alura-docker

## Módulo 01 - Introdução ao Docker
**Aula 01.01 - Introdução**

**Aula 01.02 - O problema das máquinas virtuais**
- um servidor físico gera vários problemas, entre eles o custo de luz e rede, e o seu alto tempo de ociosidade
- a virtualização veio para resolver o problema dos servidores físicos, porém, temos a desvantagem com a configuração inicial e atualizações de diversos sistemas operacionais

**Aula 01.03 - Desvantagens das máquinas virtuais**

**Aula 01.04 - A era dos containers**

**Aula 01.05 - Vantagens dos containers**

- Melhor controle do uso dos recursos do sistema operacional
- Agilidade na hora de criar e remover aplicações
- Maior facilidade na hora de trabalhar com diferentes versões de bibliotecas e linguagens


**Aula 01.06 - O que é o Docker?**

- Existe a Docker, Inc., empresa que toma conta do Docker e a tecnologia Docker dos containers.
- A Docker, Inc. no início era chamada de dotCloud que era uma empresa de PaaS (Platform as a Service) que utilizava a infraestrutura do Amazon Web Services (AWS) e introduziu o conceito de containers na hora de subir uma aplicação, dando origem ao Docker
- O Docker  é uma coleção de tecnologias, sendo `Docker Engine` a principal que faz o intermédio entre o sistema operacional, `Docker Compose`, um jeito fácil de definir e orquestrar múltiplos containers; o `Docker Swarm`, uma ferramenta para colocar múltiplos docker engines para trabalharem juntos em um cluster; o `Docker Hub`, um repositório com mais de 250 mil imagens diferentes para os nossos containers; e a `Docker Machine`, uma ferramenta que nos permite gerenciar o Docker em um host virtual.
- Quando a Docker, Inc. decidiu focar em manter o Docker tornou a tecnologia open source.

**Aula 01.07 - Tecnologias do Docker**

**Aula 01.08 - Instalando o Docker no Windows**
- Existem duas possibilidades para instalar o Docker no Windows. Temos a principal, utilizando o `Docker for Windows` e a alternativa, utilizando o `Docker Toolbox`.
- Os requisito para o Docker for Windows são:
    - Arquitetura 64 bits
    - Versão Pro, Enterprise ou Education.
    - Virtualização habilitada
- O `Docker Toolbox`  utiliza Oracle VirtualBox e  pode ser utilizados nos casos onde não possuimos os pré-requisitos

**Aula 01.09 Preparando o ambiente: Instalando Docker no Windows**

**Aula 01.10 Instalando o Docker no macOS**

**Aula 01.11 Preparando o ambiente: Instalando Docker no MacOs**

**Aula 01.12 Preparando o ambiente: Instalando Docker no Ubuntu**
```bash
# remove resões antigas
sudo apt-get remove docker docker-engine docker.io

# atualiza os pacotes
sudo apt-get update

# adiciona chave GPG oficial do repositório do Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# adiciona o repositório do Docker às fontes do APT
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

# atualiza os pacotes 
sudo apt-get update

# instala o docker
sudo apt-get install docker-ce

# verifica a versão do docker
sudo docker version

# adiciona o usuário atual ao grupo docker
sudo usermod -aG docker $(whoami)
```
**Aula 01.13 - Hello World**
```bash
docker run hello-world
```

**Aula 01.14 - Consolidando seu conhecimento**

**Aula 01.15 - Uma alternativa online**
- [https://labs.play-with-docker.com/](https://labs.play-with-docker.com/)

**Aula 01.16 - O que aprendemos?**

## Módulo 02 - Trabalhando com imagens
**Aula 02.01 - Comandos básicos com containers**
```bash
docker ps #lista os containers em execução

docker ps -a #lista todos os containers

docker run ubuntu #executa container ubuntu e para

docker run ubuntu echo "Ola Mundo" #executa container, executa comando e para

docker run -it ubuntu #executa container no modo interativo no terminal

docker start 8676d1ee5355 #inicia um container criado

docker stop 8676d1ee5355 #para o container

#inicia um container criado no modo interativo
docker start -a -i 8676d1ee5355 
```

**Aula 02.02 - Layered File System**
```bash
docker ps -a

#remove o container pelo id
docker rm 1ee1942d0e30

#remove todos os containers
docker container prune

#lista as imagens de containers
docker images

#remove a imagem hello-world
docker rmi hello-world
```

**Aula 02.03 - Comandos do Docker**

**Aula 02.04 - Sobre o Layered File System**
- Toda imagem que baixamos é composta de uma ou mais camadas.

- Essas camadas podem ser reaproveitadas em outras imagens, acelerando assim o tempo de download.

- As camadas de uma imagem são de leitura, somente os container são de leitura e escrita (os container criam uma camada acima das camadas da imagem)
