---
title: URL Validation
description: Tests whether a string is a URL. A URL must begin with http:// or https://.
tags: URL, Validation
regex: https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_\+.~#()?&//=]*)
testString: |
  http://www.google.com
  https://www.google.com
  www.google.com
---
