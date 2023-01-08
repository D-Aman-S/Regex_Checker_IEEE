---
title: E-Mail Validation
description: This might come in handy if you have email input and you want to make sure the user is entering a valid email address. Contact forms are a good example here.
tags: Email, Validation
regex: ^[\w-\.]+@([\w-]+\.)+[\w-]{2,4}$
testString: |
  Amans6963@gmail.com
  howIsItNotCorrect.co
---

There is no perfect email validator. This one's a good place to start. Do you want to see something bad? Check out [the regular expression](https://regex101.com/) for the [RFC 5322 Standard](https://www.ietf.org/rfc/rfc5322.txt).

```javascript
const rfc5322 =
	/(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])/g
```

Ouch.
