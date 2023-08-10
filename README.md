# budibase

Projeto alterado do original para rodar no docker desktop do MAC com processador M1.

Procedimento, passo-a-passo:
No site dockerhub.com, baixar o docker desktop para MAC com processador M1;
Instalar o npm através do brew com o comando: 
brew install npm

Uma vez que o docker e o npm estejam operacionais, executar os comandos: 
npm i -g @budibase/cli
 Para baixar e instalar o budi client
 
budi hosting --init
 Para inicializar o repositório gerando o arquivo de variáveis de ambiente e o docker-compose.yaml que gerará o budibase em docker
 Editar o arquivo docker-compose.yaml e incluir "platform: linux/x86_64" no app-service como no trexo do exemplo abaixo:
 services:
  app-service:
    platform: linux/x86_64
    restart: unless-stopped
    image: budibase.docker.scarf.sh/budibase/apps
    
budi hosting --start
 Aí sim já pode executar o comando acima para iniciar o budibase via docker.

 
Uma vez que já temos o budi instalado e o docker-compose.yaml ajustado, basta executar
budi hosting --start
 Para iniciar
 e 
budi hosting --stop
 Para parar

Lembrando que os comandos só funcionam no diretório onde se encontram os arquivos.
