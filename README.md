# weekly26
serverless lambda aws

### Start a new github repo, and create a lambda directory to learn AWS Lambda
```
mkdir lambda
npm init -y
npm i serverless -D
```
### Use Serverless Framework - Follow instruction 
```
mkdir serverless
cd serverless/
../node_modules/.bin/sls create --template aws-nodejs-typescript
```

### Execute Local
```
npm i

npx sls invoke local -f hello --path src/functions/hello/mock.json
```

```
Serverless: Bundling with Webpack...
asset src/functions/hello/handler.js 10.5 KiB [emitted] (name: src/functions/hello/handler)
runtime modules 931 bytes 4 modules
built modules 803 bytes [built]
  cacheable modules 677 bytes
    ./src/functions/hello/handler.ts 348 bytes [built] [code generated]
    ./src/libs/apiGateway.ts 137 bytes [built] [code generated]
    ./src/libs/lambda.ts 192 bytes [built] [code generated]
  modules by path external "@middy/ 84 bytes
    external "@middy/core" 42 bytes [built] [code generated]
    external "@middy/http-json-body-parser" 42 bytes [built] [code generated]
  external "source-map-support/register" 42 bytes [built] [code generated]
webpack compiled successfully in 181 ms
{
    "statusCode": 200,
    "body": "{\"message\":\"Hello Frederic, welcome to the exciting Serverless world!\",\"event\":{\"headers\":{\"Content-Type\":\"application/json\"},\"body\":{\"name\":\"Frederic\"}}}"
}
```
### Execute Deploy
```
npm i
npx sls deploy

```
### Result 
- I have'nt share my aws keys
- I am not seen in my aws dashboard any stack created
- I am not seen in my serverless.com account dashboard anything created
- But Here is the OK response over aws URL POST

```
curl --location --request POST 'https://wuq1544y2k.execute-api.us-east-1.amazonaws.com/dev/hello' --header 'Content-Type: application/json' --data-raw '{ "name": "Maximiliano Usich, maximilianou@gmail.com"}'
```

```
{"message":"Hello Maximiliano Usich, maximilianou@gmail.com, welcome to the exciting Serverless world!","event":{"resource":"/hello","path":"/hello","httpMethod":"POST","headers":{"Accept":"*/*","CloudFront-Forwarded-Proto":"https","CloudFront-Is-Desktop-Viewer":"true","CloudFront-Is-Mobile-Viewer":"false","CloudFront-Is-SmartTV-Viewer":"false","CloudFront-Is-Tablet-Viewer":"false","CloudFront-Viewer-Country":"AR","content-type":"application/json","Host":"wuq1544y2k.execute-api.us-east-1.amazonaws.com","User-Agent":"curl/7.64.0","Via":"2.0 9561d4f7fd20a46f9a3b03c625437a57.cloudfront.net (CloudFront)","X-Amz-Cf-Id":"Y3-t3tUKMvRYAmk2eUeAPeBroEFUbdmUVhGlGi8CWcr9zLCMl7SLgg==","X-Amzn-Trace-Id":"Root=1-60101881-1a3c05526919f3b310665b79","X-Forwarded-For":"181.44.61.193, 130.176.27.81","X-Forwarded-Port":"443","X-Forwarded-Proto":"https"},"multiValueHeaders":{"Accept":["*/*"],"CloudFront-Forwarded-Proto":["https"],"CloudFront-Is-Desktop-Viewer":["true"],"CloudFront-Is-Mobile-Viewer":["false"],"CloudFront-Is-SmartTV-Viewer":["false"],"CloudFront-Is-Tablet-Viewer":["false"],"CloudFront-Viewer-Country":["AR"],"content-type":["application/json"],"Host":["wuq1544y2k.execute-api.us-east-1.amazonaws.com"],"User-Agent":["curl/7.64.0"],"Via":["2.0 9561d4f7fd20a46f9a3b03c625437a57.cloudfront.net (CloudFront)"],"X-Amz-Cf-Id":["Y3-t3tUKMvRYAmk2eUeAPeBroEFUbdmUVhGlGi8CWcr9zLCMl7SLgg=="],"X-Amzn-Trace-Id":["Root=1-60101881-1a3c05526919f3b310665b79"],"X-Forwarded-For":["181.44.61.193, 130.176.27.81"],"X-Forwarded-Port":["443"],"X-Forwarded-Proto":["https"]},"queryStringParameters":null,"multiValueQueryStringParameters":null,"pathParameters":null,"stageVariables":null,"requestContext":{"resourceId":"wsr1tp","resourcePath":"/hello","httpMethod":"POST","extendedRequestId":"ZwjELFC0oAMFh-A=","requestTime":"26/Jan/2021:13:26:25 +0000","path":"/dev/hello","accountId":"620157586684","protocol":"HTTP/1.1","stage":"dev","domainPrefix":"wuq1544y2k","requestTimeEpoch":1611667585066,"requestId":"5504dec6-3eae-4260-b33e-bd337989dbcb","identity":{"cognitoIdentityPoolId":null,"accountId":null,"cognitoIdentityId":null,"caller":null,"sourceIp":"181.44.61.193","principalOrgId":null,"accessKey":null,"cognitoAuthenticationType":null,"cognitoAuthenticationProvider":null,"userArn":null,"userAgent":"curl/7.64.0","user":null},"domainName":"wuq1544y2k.execute-api.us-east-1.amazonaws.com","apiId":"wuq1544y2k"},"body":{"name":"Maximiliano Usich, maximilianou@gmail.com"},"isBase64Encoded":false}}
```

