---
sidebar_position: 7
---

# HTTP APIs

## Definitions
- Resource
    - An important thing you want to expose through your API
- URI (Uniform Resource Identifier)
    - A name for a resource
- Method
    - Resources have a fixed set of methods. 
- Representation
    - A protection of the state of a resource at a particular point in time.
- Media Type
    - A specific format for a representation like application/json, text/html, etc.

## HTTP Resources
There are two basic categories.
- Document
    - Represents a specific instance of a resource.  
    - Example: /customers/bob
    - These are usually subordinate resources to a collection
- Collections
    - Represents a group of related resources.
    - Example /customers
    - Can often be filtered with a query string 
        - Example /customers?state=CA
    
