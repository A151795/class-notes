---
sidebar_position: 5
---

# X-Unit

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

## Stubbing