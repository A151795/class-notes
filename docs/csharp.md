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

## Common Type Systems (CTS)
The CTS defines two broad familties of types in .NET.

### Value Types
- Have their membory managed automatically.
- Life and scope is predictable.
- The value lievs on the stack and is garbage collected when the variable goes out of scope.
- Value types are structs in C#.

### Reference Types
- Reference types have values that live on the managed heap.
- The stack has a referece to the value on the heap.
- The memory is allocated automatically and de-allocated using a garbage collector.
- Reference types in C# are classes

## Primitive Types
A list of all primitive types can be found [here](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types)

## Variable Rules
- We can write out the specific type of the variable such as `int`.
- We can also use the `var` keyword to have C# assume the type from the value
    ```csharp
    var a = "hello";
    var b = 2;
    var c = 3.2;
    ```
- C# is strictly typed.  This means that we cannot change the the type of a var after it has been set.
    ```csharp
    var a = "hello";
    a = 2; // This does not work
    ```
- `var` must be initialized everytime it is used
- `var` can only be used as a local variable and cannot be used at the class level


## Classes
- Private fields should be pre-fixed with a "_"
- Example
    ```csharp
    public class BankAccount 
    {
        private decimal _currentBalance = 0;

        public void Deposit(decimal amount) 
        {
            _currentBalance += amount;
        }

        public void Withdraw(decimal amount)
        {
            _currentBalance -= amount;
        }

        public decimal GetBalance()
        {
            return _currentBalance;
        }

    }
    ```

## Objects
- All types inherit from type System.Object.
- This means that we can pass anything as a parameter to a function if the paramter type is Object.
- That said, if a parameter is of type object, we would have to cast it to use any of the special features of sub-classes.
- Objects have two parts
- State
    - These are the variables that the object "owns"
    - In .NET, the state is made up of class level variables called fields.
- Behavior
    - Code that can be invoked and that does something with the state
    - In .NET, the behavior is made up of methods4w25

## Simple Stack/Heap overview
- Value types live on the stack.  The stack stores the name and a value for the variable.
- Reference Types have their name on the stack with the value referencing a location on the heap which has the value we want.

## Parametric Polymorphism
- When defining certain datatypes, such as a list, we need to tell it what datatype will be in the list.
- This allows us to pull items from the list and immediately do int operations on them.
```csharp
var intlist = new List<int>();
intlist.Add(42);
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

