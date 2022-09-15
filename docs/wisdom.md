---
sidebar_position: 998
---

# Programmer Wisdom

## General Wisdom
- Write the code that you wish you had
    - When developing, code how you wish the object, api, etc. would work.
    - Then go implement the object, api, etc.
- Single point of truth
    - Each piece of business knowledge should exist in exactly one place
- Single point of responsibility
    - Each code module should have a single axis of change
- Don't prematuraly create abstraction and simplifications
    - Duplicate code until we know for sure what we need
    - After we know what we need, then create functions, classes, etc.
- Just hard code it
    - Don't spend a lot of time trying to import values from configuration files.
        - This adds a lot of complexity and vulnerabilities
    - Instead, just hard code values that are not intended to be changed and deal with it.
    - Also, if you do have to change a value, it's fine because deploying software is super easy and fast now.
- Just make classes public
    - When doing application development, just make classes public.
    - In systems or framework development, you should certainly tend towards private to protect classes.
    - That said, in application development making classes public makes other app dev's job harder.

## 4 Rules of Simple Design
1. Passes the test
    - The code does what it is supposed to do
1. Reveals intention
    - The code is legible
    - A trained developer can look at the code and understand what it does
    - Does the code show what is intended
1. No duplication
14. Fewest number of elements    