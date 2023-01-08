---
title: Passwort Validation
description: Verifies that a password contains at least 6 characters, at least 1 uppercase letter, 1 lowercase letter, and 1 number with no spaces.
tags: Passwort, Validation
regex: ^((?=\S*?[A-Z])(?=\S*?[a-z])(?=\S*?[0-9]).{6,})\S$
testString: |
  Catcat1
  IAMVERYcORRECTPASSWORD
---
