#Base Image
FROM alpine

#install redis
RUN apk add --update redis

#install gcc
RUN apk add --update gcc

# run redis server
CMD ["redis-server"]