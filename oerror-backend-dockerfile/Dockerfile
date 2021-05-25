#step 1

FROM ubuntu as blah


RUN apt-get update

RUN apt-get -y install git

#RUN rm /fe_ui

RUN git clone https://github.com/dharanisubramaniam/fe_dev.git

#step2

FROM node:10-alpine as build-step

RUN mkdir /app

WORKDIR /app

COPY --from=blah fe_dev/package.json .

RUN npm install

COPY --from=blah /fe_dev .

EXPOSE 5000

CMD ["node", "index.js"]

 


