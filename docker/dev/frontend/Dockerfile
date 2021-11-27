FROM node:14-alpine
ENV HOST 0.0.0.0

RUN apk add --no-cache git
RUN apk add --no-cache openssh
WORKDIR /data
RUN git clone https://github.com/familytree365/nuxt.git --depth 1 /data/app
WORKDIR /data/app
RUN yarn install

CMD ["sh", "-c", "yarn dev"]


EXPOSE 3000
