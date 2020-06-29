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
  - Selects tests with `asdict` or `defaults` in their name.
  - Display which tests are going to be run because of `--collect-only` option.
  - Remove `--collect-only` option to run the actual tests.

## -m MARKEXPR
- Lets us run marked test together.
- Marker is best way to mark a subset of test functions.
- Marker can be any  name. for eg:
```python
import pytest

...
@pytest.mark.run_these_please
def test_memeber_access():
...

@pytest.mark.run_these_please
def test_replace():
...
```
- To run all the tests with marker `run_these_please`
```shell
$ pytest -m run_these_please
```
- Marker Expression can also be like `-m "marker1 and not marker2"`

## -x, --exitfirst
- Lets us stop the entire test session immediately when a test fails withour moving on to running next test (default behavior).
- It's uesful when debugging a problem.

## --maxfail=num
- While `-x` option stops after one test failure, `--maxfail=num` lets `num` failure happen.
```shell
$ pytest --maxfail=3
```

## --tb=no
- Turn of the traceback.

## -s and --capture=method
- `-s` flag allows print statements and its shortcut to `--capture=no`
