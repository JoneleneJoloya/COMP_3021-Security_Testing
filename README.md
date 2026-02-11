# Reflection Questions

## Question 1: Do these results match what you found in your previous peer review? Why or why not?
The results from the code scanning using the codeQL, Bandit and super-linter shows a comparable and similar issue found in the previous peer review. In the case of the python file from assignment 1 for instance, it alerts us that **url in the `get_data` function is open for permitted schemes**. For the peer review, I commented it is possible that the url may be unsafe and susceptible to being manipulated during the fetching of the remote resource (API) without proper validation. 

Moreover, the code scanning also alerts us about a **possible SQL injection vector through string-based query construction.**. Based on the OWASP guide, it explains that injection is possible when *dynamic queries or non-parameterized calls without context-aware escaping are used directly in the interpreter*. Similar to Mandeeps review, the SQL query can lead to SQL injection. This block of code has been refactored based on the suggestions of OWASP, using parameterization (which is the separation of command to code) and adding validation or error handling. 

However, some results are not reflected in the review, and upon looking at each of these code scanners, it is possible that there are certain limitations to each one. 

## Question 2: Do you think they caught all the vulnerabilities present in the code? Why or why not?


## Question 3: Why is using multiple code scanners better than using one?



### References:

- https://stackoverflow.com/questions/48779202/audit-url-open-for-permitted-schemes-allowing-use-of-file-or-custom-schemes

- https://owasp.org/Top10/2021/A03_2021-Injection/index.html
