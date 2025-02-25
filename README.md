# Java Exception Handling
Exception Handling in Java is the process of handling runtime errors so that normal program execution is not interrupted. Java provides a robust mechanism to handle exceptions using try, 
catch, finally, throw, and throws.
## What is an Exception?
An exception is an event that occurs during program execution that disrupts the normal flow. It can be caused by:

1. Invalid user input
2. Network failure
3. File not found
4. Division by zero
5. Accessing an array out of bounds

## Types of Exceptions
Java exceptions are divided into two main types:

**Checked Exceptions** – These must be handled at compile time (e.g., IOException, SQLException).
**Unchecked Exceptions** – These occur during runtime and do not require explicit handling (e.g., NullPointerException, ArrayIndexOutOfBoundsException).

# Exception Handling Keywords
Java provides five key mechanisms to handle exceptions:

🔹**try-catch**
The try block contains code that may throw an exception. The catch block handles it.
```bash
try {
    int result = 10 / 0;  // ArithmeticException
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero.");
}
```

🔹**finally**
The finally block always executes, even if an exception occurs.
```bash
try {
    int[] numbers = {1, 2, 3};
    System.out.println(numbers[5]);  // ArrayIndexOutOfBoundsException
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Index is out of bounds.");
} finally {
    System.out.println("This will always execute.");
}
```

🔹**throw**
The throw keyword is used to explicitly throw an exception.
```bash
public void checkAge(int age) {
    if (age < 18) {
        throw new IllegalArgumentException("Age must be 18 or older.");
    }
}
```

🔹**throws**
The throws keyword is used in method signatures to indicate exceptions that a method can throw.
```bash
public void readFile() throws IOException {
    FileReader file = new FileReader("data.txt");
}
```

# Common Java Exceptions
Exception -->	Description
ArithmeticException -->	Division by zero error.
NullPointerException -->	Accessing an object that is null.
ArrayIndexOutOfBoundsException -->	Accessing an invalid array index.
IOException -->	Issues in file handling.
ClassNotFoundException -->	Trying to load a class that doesn't exist.
IllegalArgumentException -->	Passing an invalid argument to a method.

# Best Practices for Exception Handling
✅ Handle exceptions at the right level – Don't catch an exception too early if the caller needs to know about it.
✅ Use specific exceptions – Avoid catching generic Exception unless necessary.
✅ Log exceptions properly – Use e.printStackTrace() or logging frameworks for debugging.
✅ Don't ignore exceptions – Always handle or propagate them properly.
✅ Use finally to close resources – Example: closing a file or database connection.

# Exercises:
## Beginner - Divide and Conquer
Create a calculator that divides two numbers entered by the user.

* Prompt the user for two integers.
* Handle division by zero using try-catch.
* If the user enters a non-integer value, catch InputMismatchException and ask again.
* Ensure the program doesn’t crash, no matter what the user enters.
* 📝 What you’ll learn: Basic try-catch, handling multiple exceptions.

## Beginner - Array Index Out of Bounds Rescue 🚀
Create an array of 5 elements and allow the user to retrieve a value based on an index they enter.

* If the user enters an index outside the array bounds, catch ArrayIndexOutOfBoundsException and ask for input again.
* Prevent infinite loops when invalid input is given.
* Use a finally block to print: "Operation complete." regardless of success or failure.
* 📝 What you’ll learn: Handling ArrayIndexOutOfBoundsException, using finally blocks.

## Intermediate - Custom Exception: Age Verification 🎂
Write a program that asks for a user's age and throws a TooYoungException if they are under 18.

* Define a custom exception class TooYoungException.
* If the user enters an invalid age (negative or non-numeric), handle it gracefully.
* If they are above 18, print: "You are old enough!"
* 📝 What you’ll learn: Creating custom exceptions, throwing exceptions explicitly.

##  Advanced - Multi-Catch Game: Rolling the Dice 🎲
Simulate a game where a user rolls a virtual dice (random number from 1-6).

* Generate a random number and divide it by another random number to introduce division errors.
* Use a multi-catch block to catch: **ArithmeticException* (if division by zero occurs), *NullPointerException* (simulate by making a null reference).
* Any other exception., print an appropriate message based on which exception occurs.
* 📝 What you’ll learn: Multi-catch blocks, catching multiple exceptions in one place.

## Hard - ATM Simulator with Exception Hierarchy 💳
Create an ATM simulator that supports multiple types of transactions.

Users should be able to:
Withdraw money
Deposit money
Transfer money
Create an exception hierarchy:
InsufficientFundsException (if withdrawal is more than balance).
InvalidAmountException (if deposit or withdrawal is negative).
UnauthorizedAccessException (if a wrong PIN is entered three times).
Implement exception handling in a way that ensures smooth user experience.
📝 What you’ll learn: Designing a proper exception hierarchy, catching & throwing multiple exceptions, structuring real-world exception handling.

## Fun Bonus Exercise:
We’ll simulate document submission using:
✅ Strings for file names instead of actual files.
✅ Integers for file size (MB) instead of real file handling.
✅ Lists for storing case records instead of a database.

You are building a legal case submission system for a law firm. Clients must provide valid details when submitting a case. Your system must handle:

1. Invalid document format – Only accept .pdf and .docx. Throw **InvalidFileFormatException** if wrong.
2. Missing documents – If no document is submitted, throw **MissingDocumentException**.
3. File size too large – If a document is over 50MB, throw **FileTooLargeException**.
4. Invalid age – Clients must be at least 18 years old. Throw **UnderageClientException**.
5. Incorrect case number format – Must be like LAW-YYYY-XXXX (e.g., LAW-2024-1234).Throw **InvalidCaseNumberException**.
6. Unauthorized case access – If a restricted case is accessed, throw **UnauthorizedAccessException**.



