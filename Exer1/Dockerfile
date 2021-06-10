#Base Image
FROM alpine

#install gcc
RUN apk add --update gcc

#install redis
RUN apk add --update redis



# run redis server
CMD ["redis-server"]