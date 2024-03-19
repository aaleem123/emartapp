FROM node:14 AS Build 
WORKDIR  /usr/src/app
COPY ./ ./client/
RUN cd client && npm install && npm run build --prod

FROM nginx:latest
COPY --from=Build /usr/src/app/client/dist/client /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf 
EXPOSE 80
