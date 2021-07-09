FROM node:16.4

# Create app directory
WORKDIR /usr/src/app

COPY ./app/package*.json ./
RUN npm ci

COPY ./app ./
RUN npm install

# Cnnot run build here, but we can copy the app-output directly into container
#RUN npm run build

EXPOSE 3000
# EXPOSE 24678
CMD ["node", "app-output/index.js"]
