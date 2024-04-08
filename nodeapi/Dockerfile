FROM node:14 AS Buildapi
WORKDIR /usr/src/app
COPY ./ ./nodeapi 
RUN cd nodeapi && npm install && npm run build --prod 

FROM node:14
COPY --from=Buildapi /usr/src/app/nodeapi ./

EXPOSE 5000
CMD ["/bin/sh", "-c", "cd /usr/src/app/ && npm start"]