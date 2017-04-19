## Language Guide
### The Basics

Swift provides its own versions of all fundamental C and Objective-C types, including **Int** for integers, **Double** and **Float** for floating-point values, **Bool** for Boolean values, and **String** for textual data.

Swift also provides powerful versions of the three primary collection types, **Array**, **Set**, and **Dictionary**, as described in [Collection Types](collectionTypes.md).

### Constants and Variables

You declare constants with the **let** keyword and variables with the **var** keyword. You can provide a **type annotation** when you declare a constant or variable
**Type inference** enables a compiler to deduce the type of a particular expression automatically when it compiles your code, simply by examining the values you provide.

```
let maximumNumberOfLoginAttempts = 10
var currentLoginAttempt = 0
let maximumNumberOfLoginAttempts : Int = 10
var welcomeMessage: String
```

### Type aliases

**Type aliases** define an alternative name for an existing type. You define type aliases with the typealias keyword:

```
typealias AudioSample = UInt16

```

### Tuples
In addition to familiar types, Swift introduces advanced types not found in Objective-C, such as **tuples**.
Tuples group multiple values into a single compound value:

 ```
 let http404Error = (404, "Not Found")
// http404Error is of type (Int, String), and equals (404, "Not Found")
 ```

### Optionals
Swift also introduces **optional** types.
You use optionals in situations where a value may be absent. An optional represents two possibilities: Either there is a value, and you can unwrap the optional to access that value, or there isn’t a value at all.

**If Statements and Forced Unwrapping :**
You can use an if statement to find out whether an optional contains a value by comparing the optional against nil.

```
if convertedNumber != nil {
    print("convertedNumber contains some integer value.")
}
// Prints "convertedNumber contains some integer value.
```
**Optional Binding :**
You use optional binding to find out whether an optional contains a value, and if so, to make that value available as a temporary constant or variable. Optional binding can be used with if and while statements to check for a value inside an optional, and to extract that value into a constant or variable, as part of a single action. if and while statements are described in more detail in Control Flow:

```
if let constantName = someOptional {
      statements
}
```

**Implicitly Unwrapped Optionals :**
Sometimes it is clear from a program’s structure that an optional will always have a value, after that value is first set. In these cases, it is useful to remove the need to check and unwrap the optional’s value every time it is accessed, because it can be safely assumed to have a value all of the time.

These kinds of optionals are defined as implicitly unwrapped optionals. You write an implicitly unwrapped optional by placing an exclamation mark **(String!)**

### Error Handling

You use error handling to respond to error conditions your program may encounter during execution.
When a function encounters an error condition, it throws an error. That function’s caller can then catch the error and respond appropriately.

```
func canThrowAnError() throws {
    // this function may or may not throw an error
}
```

### Assertions
In some cases, it is simply not possible for your code to continue execution if a particular condition is not satisfied. In these situations, you can trigger an assertion in your code to end code execution and to provide an opportunity to debug the cause of the absent or invalid value:
```
let age = -3
assert(age >= 0, "A person's age cannot be less than zero")
// this causes the assertion to trigger, because age is not >= 0
```
