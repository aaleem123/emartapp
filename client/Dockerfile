FROM node:14 AS Build 
WORKDIR /usr/src/app
COPY ./ ./client 
RUN cd client && npm install && npm run build --prod 

FROM ngnix:latest 
COPY --from=Build /usr/src/app/client/dist/client /usr/share/nginx/html
COPY nginx.conf /etc/mginx/conf.d/default.conf 

EXPOSE 4200

#first build artifact and second is to copy the artifact