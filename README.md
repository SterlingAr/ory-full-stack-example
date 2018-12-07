# ORY Hydra implementation of OAUTH2 + OpenID Connect 1.0
![](https://upload.wikimedia.org/wikipedia/en/thumb/a/a2/OpenID_logo_2.svg/1200px-OpenID_logo_2.svg.png)


## Local install 

Before running the containers, make sure the following ports are open: 9000, 9001, 9010, 9020

    $ docker-compose up -d
    
    
Check its running correctly

    $ docker logs hydra
    
    time="2018-12-07T12:54:37Z" level=info msg="Setting up http server on :4444"
    time="2018-12-07T12:54:37Z" level=warning msg="HTTPS disabled. Never do this in production."



## Performing the OAuth 2.0 Client Credentials Flow
    
Create an OAuth 2.0 Client
    
    $ docker container exec -it hydra-v1 hydra clients create \
          --endpoint http://hydra-v1:4445 \
          --id some-consumer \
          --secret some-secret \
          --grant-types client_credentials \
          --response-types token,code
          
Issue an access token

    $ docker container exec -it hydra-v1 hydra token client \
        --client-id some-consumer \
        --client-secret some-secret \
        --endpoint http://hydra-v1:4444
          
Validate the access token
       
    $ docker container exec -it hydra-v1 hydra token introspect \
         --client-id some-consumer \
         --client-secret some-secret \
         --endpoint http://hydra-v1:4445 \
         >INSERT-TOKEN-HERE<
         
        Expected output: 
        {
        	"active": true,
        	"client_id": "some-consumer",
        	"exp": 1544192099,
        	"iat": 1544188498,
        	"iss": "http://127.0.0.1:9000/",
        	"sub": "some-consumer",
        	"token_type": "access_token"
        }


           
           
       