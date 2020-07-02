# Marking Test Function
- pytest provides a cool mechanism to let us mark the test functions
- Useful for marking subset of our tests as "smoke test".
- **Smoke test** let us get a sense for whether or not there is some major break in the system. It's by convention not all-inclusive of tests.
  ```python
  @pytest.mark.smoke
  def test_list_raises():
      """list() should raise an exception with wrong type param."""
      with pytest.raises(TypeError):
          tasks.list_tasks(owner=123)


  @pytest.mark.get
  @pytest.mark.smoke
  def test_get_raises():
      """get() should raise an exception with wrong type param."""
      with pytest.raises(TypeError):
          tasks.get(task_id='123')
  ```
- Run the smoke test with `-m` option
  ```bash
  $ python -m "smoke" test_api_exceptions.py
  ```
