# Pytest options

## --collect-only
- Show which test will be run with given options and configuration.
- It's helpful to check of other options that select tests are correct before running the tests.

## -k EXPRESSION
- Lets us use an expression to find test to be run.
- We can specify prefix or suffix of test name as an expression to run all the test matching that expression.
```shell
$ pytest -k "asdict or defaults" --collect-only
```
  - Selects tests with `assdict` or `defaults` in their name.
  - Display which tests are going to be run because of `--collect-only` option.
  - Remove `--collect-only` option to run the actual tests.
