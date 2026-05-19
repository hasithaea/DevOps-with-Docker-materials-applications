FROM ubuntu

EXPOSE 5001

WORKDIR /usr/src/app


RUN apt-get update &&\
    apt-get install -y curl &&\
    curl -sL https://deb.nodesource.com/setup_16.x | bash &&\
    apt install -y nodejs &&\
    node -v && npm -v 

COPY . .

RUN npm install

RUN npm run build

RUN npm install -g serve


CMD [ "serve", "-s", "-l", "5001", "build" ]