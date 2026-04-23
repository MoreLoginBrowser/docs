### Get started with PhoneGrid Open APIs

The API function can help you programmatically perform basic functions such as quickly creating a cloud phone profile, start it or stop, and so on. It can also be used to debug or remotely control the cloud phone through ADB mode.

For more interface descriptions, please check the website.

> Open API Server endpoint: https://api.phonegrid.com

#### 1\. Get API ID and API Key

PhoneGrid integrations use a API ID and API Key to authenticate API calls:

- A API ID identifies an member.
    
- A API Key authenticates a client ID. To call PhoneGrid APIs, you'll exchange your API ID and API Key for an access token. Keep this secret safe.
    

Here's how to get your API ID and API Key:

1. Open client to get the API interface.
    
2. Copy the API ID and API key to global variables or for your app
   

{% img src="./images/image.png" alt="image.png" withLightbox=true width="" height="" /%}


#### 2\. Get access token

Exchange your API ID and API Key for an access token. The access token authenticates your app when calling PhoneGrid APIs. You can call the PhoneGrid OAuth API in any language. in the Postman app, complete the following:

1. Select the Authorization collection.
    
2. Send requests using _**Generate access_token**_
    
3. In the Post Response script, data will be automatically saved to the Globals variable. 

**Sample Response**

``` json
{
    "code": 0,
    "msg": null,
    "data": {
        "scope": "cloudphone",
        "access_token": "{{vault:json-web-token}}",
        "token_type": "Bearer",
        "expires_in": 3600,
        "client_metadata": {
            "name": "Example Team"
        }
    },
    "requestId": "4b727b1d53a445d0a46389465b562360"
}

 ```