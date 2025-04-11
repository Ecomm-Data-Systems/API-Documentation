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
