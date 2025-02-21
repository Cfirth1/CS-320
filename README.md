# CS-320
## How can I ensure that my code, program, or software is functional and secure?
To ensure that my code is functional and secure, I focus on several key areas:

Functional Testing: I use unit tests to check individual parts of my program for expected behavior. I ensure edge cases are covered and validate inputs and outputs. Automated tests, such as with JUnit, help catch issues early on.
Code Reviews: I regularly review my code, or have peers review it, to identify any potential flaws or security vulnerabilities.
Security Best Practices: I follow industry standards for security, including input validation to prevent SQL injection or other attacks, encrypting sensitive data, and managing permissions properly.
Static and Dynamic Analysis: I use static code analyzers to find potential vulnerabilities and run dynamic tests, like penetration testing, to identify runtime issues.
Through these methods, I continuously test and improve my code to ensure it functions correctly and is secure.
##  How do I interpret user needs and incorporate them into a program?
To interpret user needs, I take a user-centered design approach:

Gathering Requirements: I begin by talking to users or stakeholders to understand their goals, frustrations, and needs. This could involve interviews, surveys, or even reviewing user stories.
Prototyping: I create early prototypes or mockups of the program and gather user feedback. This helps validate the direction of the design before extensive development.
Iterative Development: I follow an agile approach to incorporate user feedback at every stage. Each iteration of the program is tested and refined based on user input to ensure it meets the expected requirements.
By maintaining constant communication with users and stakeholders, I can ensure the final product closely aligns with their needs.

## How do I approach designing software?
When designing software, I focus on these principles:

Modular Design: I break down the system into smaller, manageable modules that can be developed, tested, and maintained independently. This helps in scaling and troubleshooting.
Design Patterns: I use established design patterns such as MVC (Model-View-Controller) or Singleton where appropriate to solve common problems efficiently.
Clear Documentation: I ensure that my design decisions, code, and structures are well-documented. This helps in understanding the code later on and makes it easier for others to collaborate.
Maintainability: I focus on writing clean, readable, and reusable code to ensure the software can be easily maintained and extended in the future.
By following these principles, I can design software that is efficient, scalable, and easy to maintain.

## Project One
-https://1drv.ms/f/c/54f982c42096bc3b/Ep1Oxg8n9ixPo-WfpX-0bz4BUGCEuL8h0-m5vpFilLL2LQ?e=FV5mcc
-https://1drv.ms/f/c/54f982c42096bc3b/Ei02MjvYOlVIs6UhZ9xF_uQBTQfEZoEyWVoOdSLaMKQvgw?e=yZ85ET
-https://1drv.ms/f/c/54f982c42096bc3b/Em__6GMN_SRKm2wNm4XobRIBegL6neaPCnav_qGsz76iXg?e=k84EAv

## Project Two
-Unit Testing Approach
For each of the three features in the application, I implemented unit tests using JUnit to ensure the correctness and reliability of the code. My approach involved:
1.	Testing Valid and Invalid Inputs: Each test case covered valid scenarios as well as edge cases where invalid data was inputted.
2.	Testing Functionality and Exceptions: I verified that expected exceptions were thrown for invalid operations, ensuring robustness.
3.	Ensuring Code Coverage: By using a structured test plan, I ensured high test coverage across all functionalities.
Alignment to Requirements
My testing approach was fully aligned with the software requirements. The requirements specified that appointment IDs should be unique, descriptions should be within a character limit, and appointment dates should not be in the past. The following examples illustrate this alignment:
•	Unique ID Enforcement: The test testAddDuplicateAppointment() confirms that adding duplicate IDs results in an exception:
•	IllegalArgumentException thrown = assertThrows(IllegalArgumentException.class, () -> {
•	    service.addAppointment(new Appointment("A123", new Date(System.currentTimeMillis() + 200000), "Duplicate ID"));
•	});
•	assertEquals("Appointment ID must be unique.", thrown.getMessage());
•	Date Validation: The test testPastAppointmentDate() ensures that past dates are not allowed:
•	IllegalArgumentException thrown = assertThrows(IllegalArgumentException.class, () -> {
•	    new Appointment("A124", new Date(System.currentTimeMillis() - 100000), "Past appointment");
•	});
•	assertEquals("Appointment date cannot be in the past.", thrown.getMessage());
Effectiveness of JUnit Tests
I measured the effectiveness of my JUnit tests using code coverage analysis. My tests covered all critical functionalities, with a high coverage percentage. The inclusion of edge cases, exception handling, and functional testing ensured thorough validation of the codebase.
Writing JUnit Tests
Writing JUnit tests was a structured and iterative process. I ensured technical soundness by:
•	Using Assertions to Verify Expected Outcomes: For example: 
•	assertTrue(service.getAppointment("A123").isPresent());
•	Testing Exception Handling: 
•	assertThrows(IllegalArgumentException.class, () -> {
•	    service.deleteAppointment("A999");
•	});
Code Efficiency
I ensured my code was efficient by keeping the test cases focused and avoiding redundant checks. For instance, in testDeleteAppointment(), I validated the deletion in a minimal yet effective manner:
assertFalse(service.getAppointment("A123").isPresent());
This ensured that only necessary operations were performed, maintaining efficiency.
Reflection
Testing Techniques Employed
I employed the following software testing techniques:
•	Unit Testing: Verifying individual components in isolation.
•	Boundary Value Analysis: Checking edge cases like maximum character limits.
•	Exception Testing: Ensuring proper handling of invalid operations.
Other Software Testing Techniques
Other techniques not used in this project include:
•	Integration Testing: Validates interactions between multiple components.
•	System Testing: Tests the application as a whole.
•	Regression Testing: Ensures new changes do not break existing functionality.
Practical Uses and Implications
•	Unit Testing is best for checking isolated components.
•	Integration Testing is useful in larger applications with multiple interacting modules.
•	System Testing is critical before deploying a product.
•	Regression Testing is necessary in agile environments with frequent updates.
Caution in Software Testing
Being cautious is essential to detect edge cases and prevent failures. For example, missing an edge case like invalid appointment IDs could cause system inconsistencies. By thoroughly testing input validation, I mitigated potential runtime errors.
Limiting Bias in Testing
I minimized bias by structuring tests objectively, ensuring thorough coverage. As a developer, it’s easy to assume one’s code is correct. However, deliberate negative testing (e.g., invalid IDs, duplicate entries) counteracts this bias.
Discipline in Software Quality
Discipline is crucial in software engineering. Cutting corners in testing can lead to technical debt. To prevent this, I will:
•	Always write thorough tests for new features.
•	Perform regular code reviews.
•	Use automated testing tools for consistency.
By maintaining best practices, I can ensure long-term software quality and maintainability.
Conclusion This project reinforced the importance of structured testing in software development. By employing rigorous unit testing, I validated code correctness, efficiency, and alignment with requirements. Moving forward, I will continue emphasizing comprehensive testing to deliver high-quality software.


