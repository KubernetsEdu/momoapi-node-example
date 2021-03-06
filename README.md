# NodeJS Momo Example

## Usage

- Clone this project
- Run `npm install`
- Run `node .` to start the example application

## How it works

Currently there are two endpoints in the example application;

- `GET /pay` -> initiates a payment
- `ANY /callback` -> receives callback from mtn

## Testing the sandbox

- To test the sanbox locally, download [ngrok](https://ngrok.com). Once installed, extract it and run `./ngrok http 3000`. And leave the cli tab open
- Note the url generated by ngrok and generate a sandbox user with the url; `npx momo-sandbox --host blahblah.ngrok.com --primary-key blah-blah-uu-id`
- Note the user id and secret you receive and run the application with them;

```
CALLBACK_HOST=blahblah.ngrok.com PRIMARY_KEY=key USER_SECRET=secret USER_ID=id node .
```

- Run `curl localhost:3000`, it will request a payment on mtn api. But when you look at the ngrok tab, you'll see the callback is NOT called
- You can try with the ngrok url; `curl abc.ngrok.com`, it should create a payment and log on the ngrok terminal, visibly missing is the callback being invoked