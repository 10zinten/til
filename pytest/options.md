# Pytest options

## --collect-only
- Show which test will be run with given options and configuration.
- It's helpful to check of other options that select tests are correct before running the tests.

## -k EXPRESSION
- Lets us use expression to find test to be run.
- We can specify prefix or suffix as expression to run all the test matching that expression.
```shell
$ pytest -k "asdict or defaults" --collect-only
```
  - Selects tests with `assdict` or `defaults` in their name.
  - Display which tests are going to be run.
