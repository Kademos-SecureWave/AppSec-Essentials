# Secure Coding Fundamentals: Input Validation Guide

## **Introduction**

Input validation is a fundamental principle of secure coding that every developer should adhere to. The core concept is simple: **never trust system input**. All input to your system, whether from user interfaces, APIs, databases, or external sources, can be a potential threat. Malicious actors can exploit inputs leading to serious vulnerabilities, including injection attacks which are recognized as the top threat to software security.

## **Why Validate Inputs?**

 1. **Prevent Unknown States**: Unchecked inputs can lead to unknown states in your application, creating opportunities for attackers.
 2. **Avoid Injection Vulnerabilities**: Inputs treated as code can lead to severe security breaches.
 3. **Ensure Data Integrity**: Validation ensures that the data your application processes are accurate and appropriate for its needs.

## **Common Input Sources**

- User input via UI
- Database information
- API data
- URL parameters and cookies
- Cloud workflow data
- External images and files

## **Key Principles of Input Validation**

1. **Treat All Input as Untrustworthy**: Assume all input is potentially harmful until validated.
2. **Validate Before Use**: Check if the input meets your criteria before processing.
3. **Be Specific in Validation**: Define clear rules for what constitutes valid input.
4. **Sanitize When Necessary**: Remove harmful elements from inputs where appropriate.
5. **Use Framework-Supported Validators**: Leverage existing, tested validation functions.
6. **Encrypt Sensitive Data**: Protect data in transit between your application and external services.

## **Input Validation Techniques**

- **Type Checking**: Ensure the data type matches expected types (e.g., strings, integers).
- **Format Validation**: For specific data formats (e.g., dates, email addresses), use regex or similar methods.
- **Length Checking**: Confirm the input length is within acceptable bounds.
- **Range Checking**: Verify numbers or dates fall within reasonable, expected ranges.
- **List Checking**: Use predetermined lists for certain inputs (e.g., country names, codes).
- **Encoding & Escaping**: For inputs reflected in outputs, apply appropriate encoding to prevent XSS attacks.

## **Special Considerations**

- **Handling Non-Standard Characters**: Recognize and correctly process accents, special symbols in names, etc.
- **API and External Data Handling**: Validate external data as rigorously as your own user inputs.
- **Open Redirects**: Be cautious with URL parameters passed from external applications.
- **Memory-Safe Languages**: If possible, use memory-safe languages like Rust to avoid buffer overflow vulnerabilities.

## **Error Handling and Messages**

- Provide clear, constructive error messages without exposing raw input or internal details.
- Ensure error messages are HTML-encoded to prevent XSS.

## **Input Validation Strategy**

Building on the principles of never trusting system input, it's vital to establish a robust plan for handling every type of input. This extended guide incorporates a structured approach to input validation, ensuring security and integrity in your application.

1. **Universal Input Validation**:
    - **Validate All Inputs**: Regardless of the source, validate type, size, format, and source of the input.
    - **Server-Side Verification**: Always perform validation on the server side, not just client-side (e.g., JavaScript).
    - **Relevance and Appropriateness**: Ensure input is reasonable within your business context.
    - **Error Handling**: If input fails validation, provide a clear error message about what is expected, not what is wrong.
2. **Handling Special Characters**:
    - **Escaping Special Characters**: In cases where special characters must be accepted, use escaping functions from your framework or reliable third-party components like OWASP Java Encoder.
  
3. **Preventing CSRF Attacks**:
    - **Transaction Verification**: For any input triggering transactions (add, delete, update, etc.), verify it's not a CSRF attack by checking tokens, captchas, or re-authentication.
4. **Output Encoding**:
    - **Safe Output Display**: When input is displayed on screen, apply proper output encoding to prevent XSS attacks.
5. **Database Interactions**:
    - **Parameterized Queries**: Use parameterized queries or stored procedures for database interactions. Avoid concatenating user input with SQL commands.
6. **Redirects and Forwards**:
    - **Validate Redirect Links**: Have a pre-approved list of links for redirects. If a link isn't on the list, don't allow redirection.

## **Extended Input Validation Techniques**

- **Social Insurance Number Example**:
  - Format: `999 999 999`. Reject input with non-numeric characters, incorrect length, or special characters.
  - Log any rejection involving special characters as a potential security issue.

- **Comprehensive Flow Chart for Untrusted Data**:
  - Use a structured flow chart for validating all untrusted data as seen below:
    ![Uploaded image](https://files.oaiusercontent.com/file-2mUjmiG8qgvMY0zvTWXEYeb0?se=2024-01-15T12%3A50%3A09Z&sp=r&sv=2021-08-06&sr=b&rscc=max-age%3D299%2C%20immutable&rscd=attachment%3B%20filename%3Dimage.png&sig=/dHldfccwxutokYrFFNjEFitjsc1bUXZ16xX4mkx1rQ%3D)

## **Additional Considerations**

- **Context-Specific Encoding**: Adjust output encoding based on the context (e.g., HTML context, JavaScript strings).
- **CSRF Protection**: In-depth CSRF protection strategies are discussed in Chapter 5 of this guide.
- **Inline SQL Risks**: Understand the dangers of inline SQL and why parameterized queries are safer.

## Conclusion

Input validation is a non-negotiable aspect of secure coding. By rigorously validating every input, you minimize the risk of security vulnerabilities and enhance the overall integrity and reliability of your application. Remember, a proactive approach to input validation is a critical step in building a secure, robust application. This guide on input validation provides a detailed, systematic approach to handle all types of inputs securely. By following these practices, developers can significantly reduce vulnerabilities like injection, XSS, CSRF, privilege escalation, and business logic flaws.

----------

***This guide is part of our ongoing series on AppSec Essentials, aimed at helping beginners, enthusiasts, and professionals alike in developing secure applications. Stay tuned for more topics and deep dives into the world of application security.***
