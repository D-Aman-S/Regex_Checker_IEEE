---
title: Time HH:MM
description: Tests whether a string is a time in HH:MM format. What does that mean? It is checked whether the string consists of two numbers separated by a colon. The first number must be between 00 and 23, the second between 00 and 59.
tags: Date, TIME, Validation
regex: ^(0[0-9]|1[0-9]|2[0-3]):[0-5][0-9]$
testString: |
  00:00
  23:59
  24:00
  25:87
---

## Time and date formatting

I highly recommend that you take a look at the [moment.js documentation.](https://momentjs.com/docs/#/displaying/format/).There you will find a lot of examples and explanations on how to deal with time and date.

## Intl Object

At least as exciting is [`Intl.DateTimeFormat() constructor`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DateTimeFormat/DateTimeFormat). This constructor allows you to represent the time and date in your preferred language and format. You can even specify the time zone you want to display the time in. Clear recommendation!

Let's look at the following example:

```javascript
const date = new Date() //Thu Nov 03 2022 08:51:50 GMT+0100 (Central European Standard Time)
const options = {
	weekday: 'long',
	year: 'numeric',
	month: 'long',
	day: 'numeric',
	timeZone: 'Europe/Berlin',
	timeZoneName: 'short'
}
const formatter = new Intl.DateTimeFormat('de-DE', options)
console.log(formatter.format(date)) // Donnerstag, 3. November 2022 um MEZ
```

### What happened here?

We created a new `date` Object and stored it in the constant

> [Date documentation on MDN web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date?retiredLocale=de).

Then we created an object containing the time zone and format options `options`, stored it in the constant.

> Note: You can find out exactly what the created options like `weekday` or `timeZoneName` do in the [Intl DateTimeFormat documentation on MDN web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DateTimeFormat/DateTimeFormat).

We then created a new `Intl.DateTimeFormat` constructor and passed it the options (`options`) and the [ICU](https://www.localeplanet.com/icu/) (de-DE). Finally, we called the `format()` method and passed the date. The result is a string representing the date in German and in the format `Thursday, November 3, 2022 at CET`.
