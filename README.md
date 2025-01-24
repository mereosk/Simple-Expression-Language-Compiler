# Simple Expression Language Compiler

This project is a simple expression language compiler built with **JFlex** (for scanning tokens) and **Java CUP** (for parsing). It allows you to define functions, use conditional expressions, and perform operations like string concatenation and reversing strings. The compiler generates Java code and can handle simple input programs written in the expression language.

## Features
- **Lexical Analysis**: Recognizes identifiers, keywords (`if`, `else`, etc.), operators (`+`, `reverse`), and string literals.
- **Syntax Parsing**: Processes input programs and verifies grammar rules defined using Java CUP.
- **Code Generation**: Produces Java code that mirrors the functionality of the input program.
- **Error Handling**: Detects illegal characters and syntax errors.

---

## Project Structure
- `scanner.flex`: JFlex specification for lexical analysis.
- `parser.cup`: Java CUP grammar specification for parsing.
- `Main.java`: Entry point for the program.
- `Makefile`: Automates the build, execution, and cleanup process.

---

## Prerequisites
To run this project, ensure you have:
1. **Java Development Kit (JDK)** installed.
2. **Java CUP**:
   - `java-cup-11b.jar` for parser generation.
   - `java-cup-11b-runtime.jar` for runtime support.
3. **JFlex**: For generating the scanner.

---

## Makefile Targets
The provided `Makefile` includes the following targets:

1. **Compile**: Generates the scanner, parser, and compiles the Java files.
   ```bash
   make compile
2. **Execute**: Runs the program using the main entry point.
   ```bash
   make execute
3. **Clean**: Removes all generated files (compiled classes and temporary files).
   ```bash
   make clean

## Example Input and Output
  - **Input**
     ```bash
     if (prefix "hello" "h") reverse "olleh" else "world"

  - **Output**
  Generated Java code:
     ```bash
    public class Main {
        public static void main(String[] args) {
            System.out.println("hello".startsWith("h") ? 
                new StringBuilder("olleh").reverse().toString() : 
                "world"
            );
        }
    }
