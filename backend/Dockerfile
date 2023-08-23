# Use a imagem oficial do Node.js como base
FROM node:20

# Crie um diretório para a aplicação
WORKDIR /usr/src/app

# Copie o arquivo package.json e package-lock.json para a imagem
COPY package*.json ./

# Instale as dependências da aplicação
RUN npm install

# Copie o restante dos arquivos da aplicação
COPY . .

# Compile o projeto Nest.js e gere o schema do Prisma
RUN npx prisma generate
RUN npm run build

# Exponha a porta que a aplicação estará ouvindo
EXPOSE 3000

# Inicie a aplicação quando o contêiner for executado
CMD ["node", "dist/main"]