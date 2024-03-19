# C#
* C# Specific Notes.

# General Concepts
* Program execution starts in `static void Main()`, which can be in any class (but there should only be one `Main()` function in a C# program).
* All classes inherit from `Object`, providing some basic functions (such as `toString()`).

# Specific Concepts
## Types
Types — A structure that specifies how to interpret the contents of a variable, expression, or constant. There are two broad kinds of types, "value types" and "reference types".

Value Types — Variables with a value type hold their data directly.
* A few value types are built into C#, such as `double` or `boolean`. These are the most basic of types and cannot be broken down further.
* The programmer can define their own value types using `struct` (a collection of other value types or reference types), and `enum` (used to assign named constants to integers for better code organization).

Reference Types — Variables with a reference type hold a reference to the data they hold.
* Three reference types are built into C#: `dynamic`, `object`, and `string`.
* The programmer can define their own reference types using `class`, `interface`, `delegate`, or `record`.

Value and Reference types differ with respect to how they store data (mentioned above) and how they are copied:
* Value Types — When copied, the contents of the variable are copied to the new variable. Two seperate copies of the variable's data will exist after the copy completes.
* Reference Types — When copied, the reference is copied to the new variable. Since both references point to the same data, any modifications done to either variable's data will affect the other.

# Syntax
* C#'s syntax is a mix of both C++'s and Java's.
    * For example, access modifiers are applied to members (just like Java), while class inheritance uses C++'s syntax.
* Statically-typed. 
* Double quote strings only.
* No semicolons at the end of classes.
* Value types can only be assigned a `null` value if they are "nullable". To indicate a nullable type, place a `?` after the variable's type.
    * e.g. `public string? firstName`
* String substitution can be performed by placing a `$` in front of the string and using `{}` to surround an expression in the string:
    * Math: `$"5 + 2 = { 5 + 2 }"`
    * Function Calls: `$"It is now { DateTime.Now.ToShortTimeString() }"`
    * Variables:
        ```cs
        var name = "Aydan";
        System.Console.WriteLine($"My name is {name}!");
        ```

## Miscellaneous Syntax
* This will be split into multiple sections as it grows.
* Any syntax that isn't related to another piece of syntax can stay in here until there are enough related notes to make a new section.

### Primary Constructors
* For constructors that simply assign members, C# supports "primary constructors" to reduce the amount of writing required.
* Instead of declaring the constructor as a function, primary constructors allow the parameters of the constructor to be specified after the class name, then these parameters can be used to initialize values when they are defined.

Here is the typical way of defining a constructor:
```cs
class Number {
    double value;

    public Number(double value) {
        this.value = value;
    }
}
```

Here is the same code, with a primary constructor:
```cs
class Number(double value) {
    double value = value;
}
```

* A primary constructor is created by putting any arguments a constructor would normally take after the class name.
    * `class Number(double value)`
* The primary constructor stays with the class name if the class inherits from any other classes:
    * `class Number(double value) : IEquatable<double>`

## Conventions
* Fields are named with `camelCase` starting with a lowercase letter.
    * Private fields are often named with a leading underscore: `_likeThis`, but this is not required by Microsoft's standards.
* Properties are named with `CamelCase` starting with an uppercase letter.
* Interfaces are named starting with a capital `I`: e.g. `IEquatable`

## File Structure
* C# programs have a `.cs` extension.
    * Unlike Java, C# classes do not have to match the name of the file that contains them.
* When complied, `.cs` files are organized into a `.dll` or `.exe` file, called an "assembly". C#-specific access modifiers can be used to control the accessibility of code between assemblies.