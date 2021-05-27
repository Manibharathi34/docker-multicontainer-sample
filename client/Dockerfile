FROM node:14.14.0-alpine
WORKDIR '/app'
COPY ./package.json .
RUN npm install
COPY . .
CMD ["npm", "run", "build"]


FROM nginx
COPY ./nginx/default.conf /usr/nginx/conf.d/default.conf
COPY --from=0 /app/build /usr/share/nginx/html