---
title: js validate email
date: 2018-09-06 16:03:58
tags:
- JavaScript
categories:
- JavaScript
---



<!--more-->

<https://stackoverflow.com/questions/46155/how-to-validate-an-email-address-in-javascript>

##### regular

```js
function validateEmail(email) {
    var re = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    return re.test(String(email).toLowerCase());
}
```

##### simple

```js
function validateEmail(email) 
{
    var re = /\S+@\S+\.\S+/;
    return re.test(email);
}
```



##### HTML5

```html
<form><input type="email" placeholder="me@example.com">
    <input type="submit">
</form>
```



