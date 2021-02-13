# Google Login
Author : [Arju S Moon](http://codemaster)
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://codemaster.online)

A lightweight Google oAuth2 login modules, which can be used in your Node, Express.js Applications

  - Get Auth URL
  - Get User Profile & Access Token

### Installation

Requires [Node.js](https://nodejs.org/) v12+ to run.

Install the dependencies and devDependencies and start the server.

```sh
$ npm install node-google-login
```

### Usage

```javascript
const NodeGoogleLogin = require('node-google-login');

const config = {
  clientID:"CLIENT_ID",
  clientSecret: "CLIENT_SECRET",
  redirectURL: "REDIRECT_URL",
  defaultScope: [
    'https://www.googleapis.com/auth/userinfo.email',
    'https://www.googleapis.com/auth/userinfo.profile',
  ]
}

const googleLogin = new NodeGoogleLogin(config);

// Generate Auth URL
const authURL = googleLogin.generateAuthUrl()
console.log(authURL);

// Get User Profiles and Access Tokens by passing the Auth code recieved from generateAuthUrl(). 
// Access token & refresh token are passed along with the response object
googleLogin.getUserProfile("AUTH_CODE").then(userProfile => {
  console.log("userProfile", userProfile);
}).catch(error => {
  console.log(error);
})

```
