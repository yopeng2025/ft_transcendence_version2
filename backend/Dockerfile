FROM node:24-alpine AS dev

# Execute the following commands in Docker image environment

WORKDIR /app
COPY package*json ./
RUN npm install

COPY prisma ./prisma/
RUN npx prisma generate

COPY docker-entrypoint.sh /usr/local/bin/docker-entrypoint.sh
RUN chmod +x /usr/local/bin/docker-entrypoint.sh

COPY . .

EXPOSE 3000
ENTRYPOINT ["docker-entrypoint.sh"]
CMD [ "npm", "run", "start:dev" ]





#FROM node:24-alpine AS build

#WORKDIR /app

#COPY package*json ./
#RUN npm install

#COPY prisma ./prisma/
#RUN npx prisma generate

#COPY . .
#RUN npm run build && npx tsc 