# gitlab-ci-templates

## Including a Template in your Project:

Adding a template into your projects `.gitlab-ci.yml` file is easy. You'd just have to modify the `include` section of the yml file to have the following: 
1. The gitlab-ci-templates project.
2. The branch that the template is on.
3. The path to the template file you're adding.

```yml
include:
  - project: 'tvsre-tools/lib/gitlab-ci-templates'
    ref: main
    file:
      - '/jobs/python/lint/verify-python.yml'
```

In the example above, we're including the `verify-python.yml` file path from the branch `main`. 

**Note:** If you're replacing a job in your `.gitlab-ci.yml` file with a template, you'll have to remove that job from the file before you include the template.

## Pylint Ignore Flags (To Be Reviewed):

- [C0301](https://pylint.pycqa.org/en/stable/user_guide/messages/convention/line-too-long.html): Line too long
- [C0103](https://pylint.pycqa.org/en/stable/user_guide/messages/convention/invalid-name.html): Invalid Name
- [C0116](https://pylint.pycqa.org/en/stable/user_guide/messages/convention/missing-function-docstring.html): Missing Function Docstring
- [C0115](https://pylint.pycqa.org/en/stable/user_guide/messages/convention/missing-class-docstring.html): Missing Class Docstring
- [C0114](https://pylint.pycqa.org/en/stable/user_guide/messages/convention/missing-module-docstring.html): Missing Module Docstring
- [W1514](https://pylint.pycqa.org/en/stable/user_guide/messages/warning/unspecified-encoding.html): Unspecified Encoding
- [E0401](https://pylint.pycqa.org/en/stable/user_guide/messages/error/import-error.html): Import Error
- [W0401](https://pylint.pycqa.org/en/stable/user_guide/messages/warning/wildcard-import.html): Wildcard Import
- [C0325](https://pylint.pycqa.org/en/stable/user_guide/messages/convention/superfluous-parens.html): Superfluous-parens
- [E0602](https://pylint.pycqa.org/en/stable/user_guide/messages/error/undefined-variable.html): Undefined Variable
- [R0801](https://pylint.pycqa.org/en/stable/user_guide/messages/refactor/duplicate-code.html): Duplicate Code
- [R0903](https://pylint.pycqa.org/en/stable/user_guide/messages/refactor/too-few-public-methods.html): Too Few Public Methods
- [R0201](https://pylint.pycqa.org/en/stable/user_guide/messages/refactor/old-no-self-use.html): no-self-use replaced by [R6301](https://pylint.pycqa.org/en/stable/user_guide/messages/refactor/no-self-use.html)

### Additional Pylint Ignore Flags for Test Cases (To Be Reviewed):
- [E1129](https://pylint.readthedocs.io/en/latest/user_guide/messages/error/not-context-manager.html): not-context-manager
- [W0212](https://pylint.readthedocs.io/en/latest/user_guide/messages/warning/protected-access.html): protected-access
- [W0611](https://pylint.readthedocs.io/en/latest/user_guide/messages/warning/unused-import.html): unused-import
- [W0621](https://pylint.readthedocs.io/en/latest/search.html?q=redefined-outer-name&check_keywords=yes&area=default#): redefined-outer-name
## Flake8 Ignore Flags (to be reviewed)
- [E501](https://www.flake8rules.com/rules/E501.html): Line too long
- [E265](https://www.flake8rules.com/rules/E265.html): Block comments should start with `#`
- [W605](https://www.flake8rules.com/rules/W605.html): Invalid Es-cah-pay sequence `x`
- [E262](https://www.flake8rules.com/rules/E262.html): Inline comment should start with `#`
- [W503](https://www.flake8rules.com/rules/W503.html): Line break occurred before a binary operator
- [E111](https://www.flake8rules.com/rules/E111.html): Indentation is not a multiple of four
- [E117](https://www.flake8rules.com/rules/E117.html): Over-indented
- [E121](https://www.flake8rules.com/rules/E121.html): Continuation line under-indented for hanging indent
- [E123](https://www.flake8rules.com/rules/E123.html): Closing bracket does not match indentation of opening bracket's line
- [E126](https://www.flake8rules.com/rules/E126.html): Continuation line over-indented for hanging indent
- [E128](https://www.flake8rules.com/rules/E128.html): Continuation line under-indented for visual indent
- [E131](https://www.flake8rules.com/rules/E131.html): Continuation line unaligned for hanging indent
- [E225](https://www.flake8rules.com/rules/E225.html): Missing whitespace around operator
- [E231](https://www.flake8rules.com/rules/E231.html): Missing whitespace after ',', ';', or ':'
- [E251](https://www.flake8rules.com/rules/E251.html): unexpected spaces around keyword / parameter equals
- [E261](https://www.flake8rules.com/rules/E261.html): At least two spaces before inline comment
- [E266](https://www.flake8rules.com/rules/E266.html): Too many leading '#' for block comment
- [E271](https://www.flake8rules.com/rules/E271.html): Multiple spaces after keyword
- [E301](https://www.flake8rules.com/rules/E301.html): Expected 1 blank line, found 0
- [E302](https://www.flake8rules.com/rules/E302.html): Expected 2 blank lines, found 0
- [E303](https://www.flake8rules.com/rules/E303.html): Too many blank lines (3)
- [E305](https://www.flake8rules.com/rules/E305.html): Expected 2 blank lines after end of function or class
- [E401](https://www.flake8rules.com/rules/E401.html): Multiple imports on one line
- [E402](https://www.flake8rules.com/rules/E402.html): Module level import not at top of file
- [E711](https://www.flake8rules.com/rules/E711.html): Comparison to None should be 'cond is None:'
- [E741](https://www.flake8rules.com/rules/E741.html): Do not use variables named 'I', 'O', or 'l'
- [F401](https://www.flake8rules.com/rules/F401.html): Module imported but unused
- [F403](https://www.flake8rules.com/rules/F403.html): 'from module import *' used; unable to detect undefined names
- [F405](https://www.flake8rules.com/rules/F405.html): Name may be undefined, or defined from star imports: module
- [F811](https://www.flake8rules.com/rules/F811.html): Redefinition of unused name from line n
- [F841](https://www.flake8rules.com/rules/F841.html): Local variable name is assigned to but never used
- [W291](https://www.flake8rules.com/rules/W291.html): Trailing whitespace
- [W292](https://www.flake8rules.com/rules/W292.html): No newline at end of file
- [W293](https://www.flake8rules.com/rules/W293.html): Blank line contains whitespace
- [E712](https://www.flake8rules.com/rules/E712.html): Comparison to true should be 'if cond is true:' or 'if cond:'
- [W391](https://www.flake8rules.com/rules/W391.html): Blank line at end of file
