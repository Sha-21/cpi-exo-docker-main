FROM node:latest AS build
WORKDIR /usr/src/app
COPY ./package*.json .
RUN npm install
COPY . .
RUN npm run build
CMD ["node", "dist/main.js"]

FROM nginx:latest
COPY --from=build /usr/local/app/dist/express-gaumont /usr/share/nginx/html
