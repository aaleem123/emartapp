FROM node:14 AS nodeapi-Build 
WORKDIR /usr/src/app
COPY ./ ./nodeapi/
RUN cd nodeapi && npm install 

FROM node:14 
COPY --from=nodeapi-Build /usr/src/app/nodeapi/ ./
EXPOSE 5000
CMD ["/bin/sh", "-c", "cd /usr/src/app/ && npm install"]
