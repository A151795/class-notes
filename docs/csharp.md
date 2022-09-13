---
sidebar_position: 4
---

# C# Language

## Basic Program
```csharp
public class Program
{
    public static void Main(string[] args)
    {
        Console.WriteLine("Hello, world!");
    }
}
```

## Namespaces
- Your default namespace is the name of the project
- There can be multiple namespaces in the same file
- We can use the `using` keyword to reference other namespaces.
- We can do a filescope namespace which allows us to get rid of one level of curly brackets
- Regular Namespace
    ```csharp
    namespace MyNamespace
    {
        public class MyClass
        {

        }
    }
    ```
- Filescope Namespaces
    ```csharp
    namespace MyNamespace;
    public class MyClass
    {

    }
    ```

## Naming Convention
- PascalCase
    - Classes, records, and structs
- camelCase
    - Private fields, internal fields, and variables
- _
    - Prefix private and internal fields with an "_"
- s_
    - Prefix static fields with "s_

## Cool Lanugage Features
- `$`
    - Used for string interpolation. 
    - Example 
        ```csharp
        string name = "Max";
        Console.WriteLine($"Hello, {name}!");
        ```
- `?`
    - Used for values that may be null.
    - Example
        ```csharp
        string? name = Console.ReadLine();
        if (name != null) {
            Console.WriteLine("Name is not null");
        }
        else {
            Console.WriteLine("Name is null");
        }
        ```
- `string[first_index..last_index]`
    - Used for substrining or cutting a string. 
    - In this case last_index will be excluded
    - Example
        ```csharp
        string example = "hello world";
        string cut1 = example[0..5]; // cut1=hello
        string cut2 = example[..5]; // cut2=hello
        ```

