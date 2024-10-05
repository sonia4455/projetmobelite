FROM node:14 AS build
WORKDIR /app
COPY package*.json ./
#build
RUN npm install
COPY . . 
# mehich run juste ththar statiques mtaa page "mawjouda deja fel build:dev packege.json" mech kif npm run mtaa beck eli trani metou9efch 
RUN npm run build:dev 
# seconde stage 
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 3000
# Modifier la configuration Nginx pour écouter sur le port 3000...
RUN sed -i 's/listen       80;/listen       3000;/' /etc/nginx/conf.d/default.conf


CMD ["nginx", "-g", "daemon off;"] 
