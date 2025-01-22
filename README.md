# Codtech-Task-4
Name:Rohith Jairaam .P.C
ID:CT08HKX
Domain:c++ programming 
Duration:December 30th, 2024 to January 30th, 2025
Mentor:

# Overview of C++ programming(COMPILER DESIGN BASICS)
1. Purpose: 
   - This program is designed to evaluate mathematical expressions containing addition, subtraction, multiplication, division, and parentheses.

2. Language Used: 
   - The program is written in C++.

3. Libraries Used:
   - `iostream`: For input/output operations.
   - `string`: For handling string data.
   - `cctype`: For checking characters (e.g., `isdigit`, `isspace`).
   - `stdexcept`: For throwing runtime exceptions.

4. **Main Class**: 
   - The program defines a class `SimpleCompiler`, which encapsulates the logic for parsing and evaluating mathematical expressions.

5. **Private Members**:
   - `input`: Stores the input string (the mathematical expression).
   - `pos`: Tracks the current position of the parser in the input string.

6. **skipWhitespace()**:
   - A helper function that skips over any whitespace in the input to ensure that the parser doesn't get distracted by spaces between tokens.

7. **parseNumber()**:
   - This function parses a number (either integer or floating-point) from the input string.
   - It throws an error if no valid number is found at the current position.

8. **parseFactor()**:
   - This function handles the parsing of factors, which can either be a number or a parenthesized expression.
   - It delegates the responsibility of parsing expressions within parentheses to `parseExpression()`.

9. **parseTerm()**:
   - This function handles parsing of terms, which consist of factors multiplied or divided by other factors.
   - It supports handling `*` and `/` operators.

10. **parseExpression()**:
    - This function handles parsing of expressions, which consist of terms added or subtracted.
    - It supports handling `+` and `-` operators.

11. **Recursive Descent Parsing**:
    - The program uses recursive descent parsing, where each parsing function corresponds to a specific grammar rule (e.g., `parseExpression` for expressions, `parseTerm` for terms).

12. **Operator Precedence**:
    - The program correctly handles operator precedence:
      - Multiplication and division (`*` and `/`) have higher precedence than addition and subtraction (`+` and `-`).
      - Parentheses have the highest precedence, evaluated first.

13. **Error Handling**:
    - The program uses `runtime_error` exceptions to report issues, such as division by zero or unexpected characters.

14. **parseFactor() for Parentheses**:
    - If the current character is a parenthesis `(`, the program recursively calls `parseExpression()` to evaluate the expression inside the parentheses and expects a closing parenthesis `)`.

15. **Division by Zero Check**:
    - The program includes a check to prevent division by zero, throwing a `runtime_error` if such an operation is attempted.

16. **Expression Evaluation**:
    - After parsing, the evaluated result is returned to the caller.

17. **Main Function**:
    - The main function prompts the user to enter a mathematical expression as a string.
    - It then creates a `SimpleCompiler` object with the input string and calls `evaluate()` to compute the result.

18. **Error Messages**:
    - If an error occurs, such as an invalid character or mismatched parentheses, the program catches the exception and prints an error message with the location of the issue.

19. **Input Parsing**:
    - The user enters an arithmetic expression in a format like `3 + 5 * (2 - 8)`.

20. **Result Output**:
    - If the expression is valid, the program outputs the result of the evaluation.

21. **Expression Complexity**:
    - The program supports complex expressions, such as `3 + 5 * (2 - 8)`, where the parentheses influence the evaluation order.

22. **Function Decomposition**:
    - The program uses clear function decomposition, with each function responsible for parsing a specific component of the expression (number, term, factor, etc.).

23. **User Input**:
    - The program uses `getline(cin, expression)` to handle the input, allowing multi-character expressions.

24. **Robust Parsing**:
    - The parser ensures that invalid input results in an exception, making the program robust against malformed expressions.

25. **Extensibility**:
    - The current implementation is extensible and could be easily modified to support more operations or improve error handling.

26. **Output Format**:
    - The program outputs the computed result in a human-readable format.

27. **Testable**:
    - The program is easily testable with various expressions, and it can handle edge cases like unbalanced parentheses or invalid characters in the input.
