# Authentication

You will need to obtain the following to authenticate your API reqeust.

- subdomain
- site_token

The subdomain was set up for you when your account was set up on ecommdatasystems.com. Your site token will be used to make requests from a specific domain. Your account can have many site tokens. Meaning you can serve your online store from multiple domains.

```javascript

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function() {
  if(this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "[[subdomain]].ecommdatasystems.com/api/v1/products");
xhr.setRequestHeader("Authorization", "Bearer [[site_token]]");

xhr.send();
```


### User Authentication

If you are doing customer authentication, you will need to obtain a account_secret and keep that secure sever side for your API requests. You can add your account secret key in a server side request like this.

```javascript

'headers': {
  'Authorization': 'Bearer [[site_token]]:[[account_secret]]'
},

```


### Site Tokens

A site token is generated in your admin interface. You can have as many site tokens as you like for your account. For example. You will for sure want to have a site token for the domain of your website. But you will probably want to create a site token for your localhost, dev or staging environments. This will help ensure that only authorized domains are accessing your catalog.
