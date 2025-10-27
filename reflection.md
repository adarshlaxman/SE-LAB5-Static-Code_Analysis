 Which issues were the easiest to fix, and which were the hardest? Why?

Easiest:

Fixing style issues reported by Flake8, such as extra blank lines (E303), missing newline at end of file (W292), and trailing whitespace (W293).

These were simple formatting adjustments that did not affect the logic of the program.

Hardest:

Handling potential exceptions properly and validating input types was more challenging because it required understanding how Python handles runtime errors.

Configuring proper file handling and ensuring that files were opened and closed safely using with open() also required careful changes to avoid breaking functionality.

2. Did the static analysis tools report any false positives? If so, describe one example.

Yes.

Pylint flagged the use of the global keyword in the load_data() function as a bad practice.

However, in this specific case, it was necessary since the function needed to modify the global stock_data dictionary shared across the program.

Therefore, this warning was a false positive in the context of this simple script.

3. How would you integrate static analysis tools into your actual software development workflow?

Integrate Pylint, Flake8, and Bandit into a Continuous Integration (CI) pipeline (e.g., GitHub Actions).

Configure the pipeline to automatically run these tools whenever code is pushed or a pull request is created.

During local development, run these tools before committing code to ensure that all code meets the required quality and security standards.

Set up pre-commit hooks so that no code violating PEP8 or security guidelines can be pushed accidentally.

4. What tangible improvements did you observe in the code quality, readability, or potential robustness after applying the fixes?

Code Quality:

The updated code now follows PEP8 standards, has consistent indentation, and uses descriptive function names and docstrings.

Readability:

The addition of clear docstrings and structured comments makes the code easier to understand for future developers.

Robustness & Security:

Potential runtime and security issues (like the use of eval() and broad except: blocks) were removed.

The code now safely handles files and invalid inputs, reducing chances of crashes.

Overall:

The program became more maintainable, secure, and professional — ready for inclusion in a real-world project or CI pipeline.
