## About

Sample login, consent, logout flow with: **VueJs + AppAuth, PHP+Symfony**

Example apps used: 

[VueJs app](https://github.com/SterlingAr/openid-vuejs-client)

[PHP app](https://github.com/SterlingAr/openid-user-manager)


## Local install 

Make sure the following ports are available on  the host: **9003, 9001, 4466, 4456, 4455, 8000, 8080**

Launch containers:


    ➜  cp .env.dist .env
    
    ➜  docker-compose up -d
    


Go to **http://localhost:8080**