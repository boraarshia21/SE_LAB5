## Reflection

### 1. Which issues were the easiest to fix, and which were the hardest? Why?
- **Easiest:**  
  The easiest issues to fix were the missing **module docstring (C0114)** and the **unused import (F401)**. These required only simple edits — adding a short descriptive comment and removing an unnecessary import statement.  
- **Hardest:**  
  The hardest issues were the ones involving **dangerous default arguments (W0102)** and **file handling without `with` (W1514)**. These required understanding how Python handles mutable default parameters and file resource management. The fix involved changing the function definitions and rewriting file I/O using context managers, which needed a bit more reasoning about program flow and safety.

### 2. Did the static analysis tools report any false positives? If so, describe one example.
Yes, there was a mild false positive with **the unused import warning for `logging`**. Although the tool flagged it as unused, the intention was to potentially use logging for recording actions in the inventory system later. The warning was correct for the current state but slightly premature since the feature was planned for future enhancement.

### 3. How would you integrate static analysis tools into your actual software development workflow?
- Integrate tools like **Pylint**, **Flake8**, and **Bandit** directly into the **CI/CD pipeline** using platforms like GitHub Actions. This ensures that every commit and pull request is automatically checked for code quality and security issues before merging.  
- During **local development**, configure the editor (VS Code) to show linting warnings in real time, helping developers fix small problems immediately instead of after code review.  
- Run static analysis as part of **pre-commit hooks** using tools like `pre-commit`, ensuring code follows standards before it even reaches the repository.

### 4. What tangible improvements did you observe in the code quality, readability, or potential robustness after applying the fixes?
- The code became **safer** — by removing risky patterns like mutable default arguments and insecure functions like `eval()`.  
- It became **cleaner and more readable**, with proper function docstrings, consistent formatting, and meaningful logging potential.  
- File operations became **more reliable**, as using `with open()` ensures files close automatically even if errors occur.  
- Overall, the script now feels more **professional and maintainable**, reducing the chance of runtime crashes or silent logic bugs.
