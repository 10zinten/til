# Expecting Exceptions
- To make sure a function (especially API function) raises exception
- Always raise exception from API function if desirable type is not passed.
- Simple check for type of exception raised example.
  ```python
  def test_add_raises():
      """add() should raise an exception with wrong type param."""
      with pytest.raises(TypeError):
          tasks.add(task='not a Task object')
   ```
   - Non `Task` object is added to tasks list. `add` method should raise `TypeError` exception

- Sometime we may need to check for exception parameters.
- This let us look at exception more closely.
  ```python
  def test_start_tasks_db_raises():
    """Make sure unsupported db raises an exception."""
    with pytest.raises(ValueError) as excinfo:
        tasks.start_tasks_db('some/great/path', 'mysql')
    exception_msg = excinfo.value.args[0]
    assert exception_msg == "db_type must be a 'tiny' or 'mongo'"
  ```
  - Not only *db_type* should be `str` (passed `mysql` *db_type*), it should be either `tiny` or `mongo`.
