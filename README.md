# Reflection Questions

## Assignment 2
## Question 1: Do these results match what you found in your previous peer review? Why or why not?
The results from the code scanning using the codeQL, Bandit and super-linter shows a comparable and similar issue found in the previous peer review. In the case of the python file from assignment 1 for instance, it alerts us that **url in the `get_data` function is open for permitted schemes**. For the peer review, I commented it is possible that the url may be unsafe and susceptible to manipulation when fetching the remote resource (API) without proper validation. 

Moreover, the code scanning also alerts us about a **possible SQL injection vector through string-based query construction.** Based on the OWASP guide, it explains that injection is possible when *dynamic queries or non-parameterized calls without context-aware escaping are used directly in the interpreter*. Similar to Mandeeps review, they commented the SQL query can lead to SQL injection. This block of code has been refactored based on the suggestions of OWASP, using parameterization and adding validation or error handling. 

However, some results are not reflected in the review, and upon looking at each of these code scanners, it is possible that there are certain limitations to each one. 

## Question 2: Do you think they caught all the vulnerabilities present in the code? Why or why not?

Even if we have all the code scanners in the world it is still possible to miss certain vulnerabilities. Something that we have learned in this course, COMP-3021, one of the main principles of security is that there is no security guarantee. No application or source code is guaranteed to be secure from all attacks or exploitation of vulnerabilities. Therefore, I do not believe that we can catch all the vulnerabilities present in this source code. Furthermore, as we mitigate or resolved these insecurities there is also a possibility to introduce more vulnerabilities. All we can do now as a developer is to always keep in mind to design application while keeping security as the forefront of our minds. Furthermore, habitually pratice the fundamental security principles and coding standards so that it would be easier for the next junior developers handling and testing the source code or application. 

## Question 3: Why is using multiple code scanners better than using one?

Every code scanner is designed to analyze certain aspects of the source code with various tools and certain modules. For example, the bandit helps find common security issues in python code by building abstract syntax trees (AST) from it and running appropriate plugins against AST nodes. However, some code scanners produce overlapping results with other code scanners or linters, like how the super-linter uses various tools for their analysis reports. Though it is better to use more than one code scanner to detect vulnerabilities and errors, in case one of the code scanners are not designed to capture a specific vulnerability in the source code that could cause a breach down the line. 

## Assignment 3
## How did the AppScan CodeSweep scan performance compare to the previous code scanners you used?
AppScan CodeSweep seems convenient as it scans and presents the security issues as soon as you make changes and save the file, probably due to the application directly installed within VS Code. 
Furthermore, it provides a clean and colour-coded interface to identify what type of security issue is present in the source code. For example, there is a security issue about the hardcoded credentials which we have noticed during the peer review. This is highlighted and noted in red. On the otherhand, the typescript issue in regards to the standard input in line 15 is highlighted and noted in orange. 


### References:

- Stack overflow - Audit url open for permitted schemes. Allowing use of "file:" or custom schemes is often unexpected:
https://stackoverflow.com/questions/48779202/audit-url-open-for-permitted-schemes-allowing-use-of-file-or-custom-schemes

- OWASP: A03:2021 - Injection:
https://owasp.org/Top10/2021/A03_2021-Injection/index.html

- Parameterizing MySQL Queries in Node:
https://blogs.oracle.com/mysql/parameterizing-mysql-queries-in-node

- Bandit security - Github:
https://github.com/PyCQA/bandit

- Super-linter - Github:
https://github.com/super-linter/super-linter

- CodeQL and CodeQL queries- Github:
https://codeql.github.com/
https://github.com/github/codeql

- Principles of Security:
https://learn.rrc.ca/d2l/le/content/702614/viewContent/11089901/View

- HCL AppScan Solution:
https://www.hcl-software.com/appscan/home