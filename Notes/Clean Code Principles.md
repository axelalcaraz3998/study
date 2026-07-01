Tags: #ComputerScience #SoftwareDesignAndArchitecture 

Clean code is a term used to refer to code that is easy to read, understand, and maintain. Writing clean, maintainable code is essential for building robust software that stands the test of time.
# Avoid Hard-Coded Numbers
Use name constants instead of hard-coded values. Write constants with meaningful names that convey their purpose. This improves clarity and makes it easier to modify the code.
# Use Meaningful and Descriptive Names
Choose names for variables, functions, and classes that reflect their purpose and behavior. This makes the code self-documenting and easier to understand without extensive comments.
# Use Comments Sparingly and Make Them Meaningful
You don't need to comment obvious things. Excessive or unclear comments can clutter the codebase and become outdated, leading to confusion and a messy codebase.
# Write Short Functions That Only Do One Thing
Follow the single responsibility principle, which means that a function should have one purpose and perform it effectively. Functions are more understandable, readable, and maintainable when they have only one job. It also makes testing them very easy.

If a function becomes too long or complex, it is better to break it down into smaller, more manageable functions.
# Follow the DRY (Don't Repeat Yourself) Principle
Avoid writing the same code more than once. Instead, reuse your code using functions, classes, modules, libraries, or other abstractions. This makes your code more efficient, consistent, and maintainable. It also reduces the risk of errors and bugs, as you only need to modify your code in one place when you update it.
# Follow Established Code-Writing Standards
Know your programming language's conventions for spacing, comments, and naming. Most programming languages have community-accepted coding standards and style guides.
# Encapsulate Nested Conditionals into Functions
One way to improve the readability and clarity of functions is to encapsulate nested if/else elements into other functions. Encapsulating such logic into a function with a descriptive name clarifies its purpose and simplifies code comprehension, it also makes it easier to reuse, modify, and test the logic without affecting the rest of the function.
# Refactor Continuously
Conduct regular code reviews and refactor your code to improve its structure, readability, and maintainability. Consider the readability of your code for the next person who will work on it, and always leave the codebase cleaner than you found it.
# Use Version Control
Version control systems meticulously track every change made to your codebase, enabling you to understand its evolution and revert to previous versions if needed. This creates a safety net for code refactoring and prevents accidental deletions or overwrites.
# References
## Articles
- [What Is Clean Code? A Guide to Principles and Best Practices](https://blog.codacy.com/what-is-clean-code)
## Websites
- [Summary of 'Clean code' by Robert C. Martin](https://gist.github.com/wojteklu/73c6914cc446146b8b533c0988cf8d29)

[[Software Design and Architecture MOC]]