# To po HTTP
# FROM node:alpine
# RUN apk add --no-cache git
# RUN apk add --no-cache openssh
# WORKDIR /data
# RUN git clone https://github.com/TomaszSmyk/Simpleweb.git /data
# RUN npm install
# EXPOSE 8080
# ENTRYPOINT npm run start

# To po ssh
FROM node:alpine
RUN apk add --no-cache openssh-client git
WORKDIR /data
RUN mkdir -p -m 0600 ~/.ssh && ssh-keyscan github.com >> ~/.ssh/known_hosts
RUN --mount=type=ssh git clone git@github.com:TomaszSmyk/Simpleweb.git /data
RUN npm install
EXPOSE 8080
ENTRYPOINT npm run start