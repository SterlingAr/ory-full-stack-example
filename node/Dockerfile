FROM node:lts-stretch

RUN apt-get update --yes \
    && apt-get install --yes git yarn


RUN git clone https://github.com/SterlingAr/openid-vuejs-client /root/js_app

WORKDIR /root/js_app

RUN npm install

EXPOSE 8080