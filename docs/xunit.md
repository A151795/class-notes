---
sidebar_position: 5
---

# Testing and x-Unit

## Terminology
- SUT: Subject Under Test
- Unit Test: Tests a very small piece of functionality in a very specific scenario without relying on any other tests to set up the world.

## A Basic Test
- Example
```csharp
public class UnitTest
{
    [Fact]
    public void Test()
    {
        // Given (Arrange)
        // This is creating the world that we want to test in
        int a = 10, b = 20, answer;

        // When (Act)
        // What we are testing
        answer = a + b;

        //Then (Assert)
        Assert.Equal(30, answer);
    }

    [Theory]
    [InlineData(10, 20, 30)]
    [InlineData(3, 3, 6)]
    public void Addition(int a, int b, int expected)
    {
        int answer = a + b;
        Assert.Equal(expected, answer);
    }
}
```

## Runnings Tests
- [Fact]
    - Turns a function in a unit test class into a test.
    - As along as the function executes and completes without an exception, the test will pass.
- [Theory]
    - Allows us to pass paramters into a test and then test the test with many parameter sets.
- If we put a constructor in a test class, xUnit will re-run that constructor for every single Fact and Theory.
    - This allows us to re-create a unique world for every test without code repition

## Test Doubles
### Dummies
A dummy is just an attribute or method parameter that does not have behavior and is never called.  It merely exists to make the SUT run correctly.  For example say we are testing the object Fruit.  Fruit must take a name as a parameter, but the function that the parameter is used in is never called during the test.  This means that said parameter is irrelevant to the SUT.
```csharp
class Fruit {
    private readonly string _name;
    public Fruit(string name) {
        _name = name
    }

    // SUT
    public int NumberOfSeeds()
    {
        return 11;
    }

    public string Name() {
        return _name;
    }
}
var myFruit1 = Fruit(null);
var myFruit2 = Fruit("Ignored String For Testing");
var myFruit3 = Fruit(new Object());
var myFruit4 = Fruit(string.Empty);
```
### Fakes
Fakes are used when we want to replace working implmentations of something that our SUT uses.  For example, if Fruit has a method that pulls from the database, that would be unnecessary and slow down our tests.  We are not trying to test wheter or not database accesses work, we are trying to test our code.  In this case, we could pass a Fake implementation of the method that grabs the data from the database with one that just returns a value.  This helps us to verify that the logic of our code is sound while avoding unnecessary database accesses or other expensive actions.
```csharp
class Fruit {
    
    // SUT
    public int NumberOfSeeds()
    {
        return 11;
    }

    public string Name() {
        return _name;
    }
}
var myFruit1 = Fruit(null);
var myFruit2 = Fruit("Ignored String For Testing");
var myFruit3 = Fruit(new Object());
var myFruit4 = Fruit(string.Empty);
```
### Mocks
A mock is a class that implements the same interface as the dependency of our SUT does.  If there is a dependency that is either unimplemented, reliant on dynamic data, etc, we need to create a mock so that our test has consistent outcomes.  Mocks essentially test the connection between various services, and also allow us to test edge cases easily.  Once the mock implements the save interface, we can specify what values it should return or exceptions it should throw instead of the normal service behvaior.  The use case of mocks is to figure out whether or not certain functions were run or not.
```csharp
interface IDoStuff(){
    public void DoSomething();
    public void DoThings();
}

class SUT{
    public SUT(IDoStuff iDoStuff){
        // Construct
    }

    public void TheThing(){
        // The Thing
    }
}

var mock = new Mock<IDoStuff>();
mock.Setup(c => c.DoSomething()).Returns(32)
```
### Stubbing
Stubs are just like mocks in that they implement the same interface as the services do.

