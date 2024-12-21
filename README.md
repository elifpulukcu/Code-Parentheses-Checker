# Parenthesis Checker (Java)

A small Java program that reads a **Java source code file** (or any text file) and verifies the **correctness of parentheses** (round `()` and curly `{}` brackets). The program stores each character in a `char[]`, pushes opening parentheses onto a stack, and pops/compares them upon encountering closing parentheses. It then reports whether the parentheses are correctly matched.

## Table of Contents

1. [About](#about)
2. [Features](#features)
3. [Project Structure](#project-structure)
4. [Dependencies](#dependencies)
5. [Usage](#usage)
6. [How It Works](#how-it-works)
7. [Contributing](#contributing)

---

## About

This repository contains:
- A **Main** class that prompts for a file path, reads its entire content, and then checks the **balance of parentheses** in the source text.
- A custom **`myStack`** class (generic stack implementation) used to push and pop brackets.  
- Clear **inline documentation** explaining each method, including **exception handling** for file operations and stack underflow conditions.

Whether you are learning **data structures**, **file I/O**, or simply want a small example of **Java** console-based programs, this project provides a straightforward demonstration of **stack usage** and **error handling**.

---

## Features

1. **File I/O**  
   - Uses `Scanner` and `Files.readAllBytes()` to read the entire content of a file specified by the user.
   - Handles missing or unreadable files using `try-catch` blocks.

2. **Custom Stack Implementation (`myStack`)**  
   - Generic class supporting `push()`, `pop()`, `peek()`, and `isEmpty()`.
   - Automatically **resizes** when adding or removing elements.

3. **Parenthesis Matching**  
   - Detects opening brackets (`(` or `{`) and pushes them onto the stack.
   - On encountering a closing bracket (`)` or `}`), pops from the stack and checks for correctness.
   - Prints an **informative message** if brackets do not match, are out of order, or if the stack is empty prematurely.

4. **Inline Visualization**  
   - After **each push**, prints the current stack content to the console for clarity.
   - Reports on final stack status to determine correctness.

---

## Project Structure

```
.
├── Main.java             # Entry point: asks user for file path, reads content, checks parentheses
├── myStack.java          # Generic stack implementation with auto-resizing
└── (Any sample .java file to test or additional .txt files)
```

---

## Dependencies

- **Java 8+**  
  Should compile and run under any modern Java version supporting your environment.

No external libraries are strictly required beyond core Java. If you wish to alter file reading logic, ensure you have the appropriate imports (`java.nio.file` etc.) available.

---

## Usage

1. **Compile**  
   ```bash
   javac Main.java myStack.java
   ```
2. **Run**  
   ```bash
   java Main
   ```
3. **Enter the File Path**  
   - For example: `C:\SampleCode1.java` (Windows) or `/Users/username/SampleCode1.java` (macOS/Linux).  
   - The program then reads the file’s contents into a `String`, passes it to `parenthesisChecker()`, and processes each character.

4. **Observe Outputs**  
   - On each **push**, the console shows the current stack contents.  
   - If any **mismatch** occurs (e.g., `(` encountered but `}` found), the program reports it immediately.  
   - When all parentheses have been processed, a final message indicates whether the parentheses are correctly matched.

---

## How It Works

1. **Reading the Input**  
   - The user supplies the file path via the console.  
   - `Files.readAllBytes(Paths.get(path))` loads the file’s entire content into a `String`.

2. **Stack Operations**  
   - **Push**: If the character is an opening bracket, it is added to `myStack`.  
     - The code prints the stack content after each push.  
   - **Pop & Check**: If the character is a closing bracket, it pops the top item and compares.  
     - If no match or the stack is empty prematurely, we know there is an error.

3. **Final Check**  
   - If the stack is empty at the end and no mismatch flags were set, **“Parentheses are correct.”** is printed.  
   - Otherwise, you’ll see **“Parentheses do not match.”** with an appropriate explanation.

4. **`myStack` Internals**  
   - Implements `Iterable<Item>` to allow **for-each** loops over the stack’s elements.  
   - Resizes automatically to avoid overflow (like an `ArrayList`).  
   - Throws `NoSuchElementException` if a `pop()` or `peek()` is attempted on an empty stack.

---

## Contributing

1. **Fork** the repository to your own GitHub account.  
2. **Create a new branch** (`feature/your-improvement`) for your changes.  
3. Commit and push to your branch.  
4. **Open a Pull Request** to merge your changes.

Please ensure your code is clean, well-documented, and tested before submitting!

---

Enjoy ensuring your Java sources have correct parentheses! If you have any questions, please open an [issue](../../issues) or reach out to the project maintainer.
