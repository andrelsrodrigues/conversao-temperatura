# Versão 16.13.2 fixa evita que atualizações futuras mudem o comportamento da aplicação.
# Denominada build para isolar imagem a ser utilizada para instalação (npm install), que ocupa mais espaço.
FROM node:16.13.2 as build 
# Criação e navegação para diretório app dentro da imagem Docker.
WORKDIR /app
# Cópia dos arquivos de instalação de bibliotecas para o diretório corrente (./).
COPY package*.json ./
# Instalação dos pacotes de acordo com os arquivos copiados no passo anterior em camada específica da imagem.
RUN npm install
# Cópia dos demais arquivos presentes em src para o WORKDIR do container (/app).
COPY . .

# Versão 16.13.2 fixa evita que atualizações futuras mudem o comportamento da aplicação.
# FROM node:16.13.2-alpine as exec
# Criação e navegação para diretório app dentro da imagem Docker.
# WORKDIR /app
# Cópia dos arquivos da pasta app da imagem intermediária build para o WORKDIR da imagem atual.
# COPY --from=build /app .

# Abertura da porta 8080 do container.
EXPOSE 8080
# Comando padrãp de execução do container.
CMD ["node", "server.js"]