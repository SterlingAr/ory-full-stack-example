# ORY STACK
![](./logo.png)


## Must read

This project works in tandem with the following projects: 
    
  - [WebApp with AppAuth](https://bitbucket.org/roiupagency/openid-webapp/src/master/)  
  - [Identity Manager](https://bitbucket.org/roiupagency/openid-identity-manager/src/master/)  

The examples provided are: 

    - Login
    - Logout
    - API request through Oathkeeper proxy
    
First, create the Hydra OAuth2 client in **resource/*

### [Login Flow explanation](https://www.ory.sh/docs/hydra/login-consent-flow)

### [LogOut Flow explanation](https://www.ory.sh/docs/next/hydra/oauth2#logout)

### [API request through Oathkeeper proxy](https://www.ory.sh/docs/oathkeeper/)


## Local install 

-  Launch containers:

    
    $ cp .env.dist .env
    
    
    $ docker-compose up -d
    
   

-  Create the Hydra, Oathkeeper and Keto resources in  **resources/**


         