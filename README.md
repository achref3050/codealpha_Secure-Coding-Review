#Introduction:

This project is part of an internship task focused on secure coding practices. The objective is to identify security vulnerabilities in a given PHP application, provide recommendations for secure coding, and implement those recommendations. The project involves uploading both the vulnerable and revised versions of the code to GitHub, along with a detailed explanation of the changes made.


Vulnerable Code

Explanation of Vulnerabilities and Fixes:

The original PHP code retrieves a secret based on the provided id parameter without verifying if the user is authorized to access that secret. This can allow attackers to manipulate the id parameter to view secrets belonging to other users.

Vulnerabilities Identified
1)SQL Injection:

The code directly uses user input ($id) in SQL queries without proper sanitization or prepared statements. This allows attackers to manipulate the query and potentially access unauthorized data.

2)Lack of Authorization Check:

The code does not verify if the user is authorized to view the secret associated with the provided id. This can allow users to access secrets that do not belong to them.

3)Exposing Sensitive Information:

Secrets are displayed directly without any form of access control, making sensitive data vulnerable to unauthorized access.



Revised Code
The revised code addresses the identified vulnerabilities by implementing prepared statements, adding authorization checks, and incorporating proper error handling.

Key Fixes
1)Using Prepared Statements:

Prepared statements help prevent SQL injection by separating SQL logic from the data. Instead of concatenating user input directly into the query, use placeholders and bind parameters.

2)Authorization Check:

We have to ensure that the current user is authorized to access the requested secret by verifying the user_id.

3)Error Handling:

We have to implement proper error handling to avoid exposing sensitive information.

4)Output Encoding:

Encode output to prevent Cross-Site Scripting (XSS) attacks.






Conclusion
This project highlights the importance of secure coding practices in web application development. By identifying and addressing vulnerabilities such as SQL injection, lack of authorization checks, and improper error handling, we can significantly enhance the security of the application. Using prepared statements, validating and sanitizing input, and implementing proper error handling are essential practices to protect against common security threats.



