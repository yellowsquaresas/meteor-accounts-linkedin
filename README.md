meteor-accounts-linkedin
============================

A meteor package for LinkedIn's login service.

Install
-----------
```
meteor add yellowsquare:accounts-linkedin
```

Configure
-----------
```
meteor add service-configuration
```
In your imports/startup/server/index.js file:
```javascript
var oauth = Meteor.settings.private.oauth;
ServiceConfiguration.configurations.upsert(
    {service: oauth.serviceName},
    {
        $set: {
            clientId: oauth.clientId,
            loginStyle: oauth.loginStyle,
            secret: oauth.secret
        }
    }
);
```
In your configuration (settings.json) :
```json
"private" : {
    "oauth" :
        {
            "serviceName" : "linkedin",
            "clientId"    : "",
            "secret"      : "",
            "loginStyle"  : "popup"
        }
}
```

License
-----------
[MIT](https://github.com/PauliBuccini/meteor-accounts-linkedin/blob/master/LICENSE)

