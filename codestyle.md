# Code Style Guide

**Source**: This code style guide references the official standards from the following sources:

- **Google Java Style Guide**: https://google.github.io/styleguide/javaguide.html
- **Oracle's Code Conventions for Java**: https://www.oracle.com/java/technologies/javase/codeconventions-intro.html
- **Alibaba Java Coding Guidelines**: https://alibaba.github.io/Alibaba-Java-Coding-Guidelines/

This style guide aims to provide a unified coding standard for all team members to improve readability, maintainability, and reduce errors in our codebase.

------

## 1. General Code Structure

### 1.1 File Naming

- Java file names should match the class name and use PascalCase (e.g., `BookInfoController.java`).
- Non-public classes should be placed in the same file as the public class they are used with, if feasible.

### 1.2 Class and Interface Names

- Use PascalCase for class and interface names (e.g., `BookInfoService`, `AdminController`).
- Class names should typically be nouns, and interface names may include verbs (e.g., `Runnable`).

### 1.3 Method Names

- Use camelCase for method names, starting with a verb to indicate actions (e.g., `addBook`, `updateBookInfo`).
- Methods performing boolean checks should use `is`, `has`, or `can` as prefixes (e.g., `isAvailable`, `hasAccess`).

### 1.4 Variable Naming

- Use camelCase for variable names, making them descriptive to enhance readability (e.g., `bookList`, `pageNumber`).
- Constants should be in `ALL_CAPS_WITH_UNDERSCORES` and placed at the start of the class (e.g., `MAX_SIZE`, `TIMEOUT`).

------

## 2. Formatting and Indentation

### 2.1 Line Length

- Keep lines under 100 characters to enhance readability across different screen sizes.

### 2.2 Indentation

- Use 4 spaces for indentation; do not use tabs.

### 2.3 Spacing

- Place a single space after commas, and a single space before and after operators.
- Avoid unnecessary blank lines; however, use blank lines to separate different sections or logical blocks.

### 2.4 Braces

- Opening braces

   go on the same line as the declaration (Allman style).

  ```java
  public void exampleMethod() {
      // code here
  }
  ```

- **Braces are required** for all control structures (e.g., `if`, `else`, `for`), even for single statements.

### 2.5 Annotations

- Annotations should be on their own line, above the element they annotate, without indentation:

  ```
  java复制代码@Override
  public void someMethod() {
      // code here
  }
  ```

------

## 3. Documentation and Comments

### 3.1 Class and Method Documentation

- Each public class and method should have Javadoc comments explaining the purpose and functionality.

  ```java
  /**
   * Fetches a list of books based on the given name.
   * @param bookName the name of the book to search
   * @return List<BookInfo> a list of books with matching names
   */
  public List<BookInfo> getBookByName(String bookName) { ... }
  ```

### 3.2 Inline Comments

- Use inline comments to clarify complex code sections only, avoiding redundant or obvious comments.

------

## 4. Exception Handling

- Handle exceptions thoughtfully, providing meaningful messages and logging wherever possible.
- Prefer `try-with-resources` for handling resources (e.g., I/O) where possible.

```java
try (BufferedReader reader = new BufferedReader(new FileReader("file.txt"))) {
    // Process file
} catch (IOException e) {
    logger.error("File read error", e);
}
```

------

## 5. Common Practices

### 5.1 DRY Principle

- Avoid code duplication by refactoring commonly used code into methods or classes.

### 5.2 Proper Use of `final`

- Mark variables as `final` if they do not need to be reassigned, improving clarity and thread safety.

### 5.3 Collections and Generics

- When using collections, specify types using generics to enforce type safety (e.g., `List<BookInfo>` instead of `List`).
