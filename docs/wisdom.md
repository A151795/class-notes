---
sidebar_position: 7
---

# Programmer Wisdom
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
    - Instead just hard code values and deal with it.  In most cases, values don't change this much.