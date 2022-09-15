---
sidebar_position: 5
---

# Testing and x-Unit

## Unit Tests
- Each unit tests needs to run in a void and cannot rely on any unit tests to set up the world we want to run in.

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
### Why do we need test doubles?
- Sometimes when working within a collaborative project, our functionality is dependent on another piece of code that happens to be incomplete.  In order to test our code, we need the other functionality to be implemented in our code, but the other functionality will not change the result of our test.  In this case, test doubles can be used to make a fill in fore the incomeplete code.  Using a test double confirms that the "connections" between the services is good, and the remaining code just need to be written.
- We also need to be able to simulate various events such as a specific date and time, an error, etc.
### Dummies
Dummies are test doubles that are place holders so that we don't get a null reference exception.  They are not involved in the test whatsoever.  They just exist to be everything else work.
### Stubbing
Stubs are test doubles that provide "canned" respo nses to particulat questions.  They help to test the "connection" between services using a "secret" code. An example would be if you requested a bonus for a 5000 balance and an amount of 69, return 50.
### Mocks
Mocks are test doubles that record everything that happens to htem.  You can ask them after the "when" portion of the test.
### Fakes
Not used in unit testing, but more for integration testing.  They replace an expensive thing tha tyou dont need to test, but your code needs.

## Stubbing
- Stubbing is a way to fake data or behavior in a unit test
- Stubbing is used when
    - A piece of data is changing, such as a date or time, which changes the result of a funciton.  In a case such as this, we can stub in a chosen date that the function will use as opposed to getting the current date
    - A piece of functionality is not written yet, but the object that the test is using requires that piece of functionality even though said functionality will not affect the result of the test.  Stubbing can help to imitate that piece functionality. That the code is operating....