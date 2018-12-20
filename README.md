# ORY STACK
![](https://upload.wikimedia.org/wikipedia/en/thumb/a/a2/OpenID_logo_2.svg/1200px-OpenID_logo_2.svg.png)


## Local install 

This will launch Hydra, Keto and Oathkeeper with minimal configuration:


    $ docker-compose up -d


##Hydra
#### Performing the OAuth 2.0 Client Credentials Flow
    
Create an OAuth 2.0 Client
    
    $ docker container exec -it hydra-v1 hydra clients create \
          --endpoint http://hydra-v1:4445 \
          --id some-consumer \
          --secret some-secret \
          --grant-types client_credentials \
          --response-types token,code
          
Issue an access token

    $ docker container exec -it hydra hydra token client \
        --client-id some-consumer \
        --client-secret some-secret \
        --endpoint http://hydra:4444
          
Validate the access token
       
    $ docker container exec -it hydra hydra token introspect \
         --client-id some-consumer \
         --client-secret some-secret \
         --endpoint http://hydra:4445 \
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


           
##Oathkeeper
    //TODO
    
##KETO
    //TODO
         