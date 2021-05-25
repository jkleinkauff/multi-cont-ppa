FROM node:15.8-alpine3.13 as builder

WORKDIR /app

COPY package.json .
RUN npm install

COPY --chown=node:node . .

RUN npm run build
#adadsa
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html