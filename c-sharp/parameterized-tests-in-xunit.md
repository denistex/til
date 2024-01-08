# Parameterised Tests In xUnit

xUnit uses the `[Fact]` attribute to denote a parameterless unit test,
which tests invariants in your code:

```csharp
public class CalculatorTests
{
    [Fact]
    public void CanAdd()
    {
        var calculator = new Calculator();

        int value1 = 1;
        int value2 = 2;

        var result = calculator.Add(value1, value2);

        Assert.Equal(3, result);
    }
}
```

In contrast, the `[Theory]` attribute denotes a parameterised test that
is true for a subset of data. That data can be supplied in a number of
ways, but the most common is with an `[InlineData]` attribute.

```csharp
[Theory]
[InlineData(1, 2, 3)]
[InlineData(-4, -6, -10)]
[InlineData(-2, 2, 0)]
[InlineData(int.MinValue, -1, int.MaxValue)]
public void CanAddTheory(int value1, int value2, int expected)
{
    var calculator = new Calculator();

    var result = calculator.Add(value1, value2);

    Assert.Equal(expected, result);
}
```

See also:

[Creating parameterised tests in xUnit with [InlineData], [ClassData], and [MemberData]](https://andrewlock.net/creating-parameterised-tests-in-xunit-with-inlinedata-classdata-and-memberdata/)
