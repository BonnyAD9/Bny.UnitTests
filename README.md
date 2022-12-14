# Bny.UnitTests
Bny.UnitTests is a library that makes unit testing in C# simpler.

## In this repository
- **Bny.UnitTests** - the library
- **Bny.UnitTests.Tests** - unit tests
- **Bny.UnitTests.Examples** - example usage
- **Documentation** - Doxygen generated documentation

## How to use
- for detailed examples see **Bny.UnitTests.Examples**

### Prepare your test classes
```C#
[UnitTest] // mark test classes with the [UnitTest] attribute
class TestSomething
{
    [UnitTest] // mark test functions with the [UnitTest] attribute
    static void Test_SomePart(Asserter a)
    { // all the test functions must have signature same as Action<Asserter>
        a.Assert(/* your assertion */);
        a.Assert(/* your next assertion */);
        // ...
    }
    
    [UnitTest]
    static void Test_OtherPart(Asserter a)
    {
        a.Assert(SomeHelperFunction(/* parameters */));
        // ...
    }
    
    static bool SomeHelperFunction(/* parameters */) { /* ... */ }
}

[UnitTest]
class TestSomethingElse { /* ... */ }
```

### Run all the tests
Use the `Tester.TestAll` method to run all the tests in all the classes with the `[UnitTest]` attribute
```C#
Tester.TestAll();
```

#### Tester.TestAll parameters
- `logAmount`: changes the amount of information written to the output
  - default value is `LogAmount.Default`
- `@out`: the output writer
  - default value is `null` which means `Console.Out` (standard output stream)
- `formatted`: determines whether the output is formatted with ANSI escape codes (colors)
  - default value is `true`

## Example output
(Default parameters)
![image](https://user-images.githubusercontent.com/46282097/204138348-4fbbebc5-bb2b-45ab-b6b6-37771271a8ca.png)

## How to get it
This library is available as a [NuGet Package](https://www.nuget.org/packages/Bny.UnitTests/)

## Links
- **Documentation:** [Doxygen](https://bonnyad9.github.io/Bny.UnitTests/)
- **Author:** [BonnyAD9](https://github.com/BonnyAD9)
- **Github Repository:** [Bny.UnitTests](https://github.com/BonnyAD9/Bny.UnitTests)
- **NuGet Package:** [Bny.UnitTests](https://www.nuget.org/packages/Bny.UnitTests/)
- **My Website:** [bonnyad9.github.io](https://bonnyad9.github.io)
