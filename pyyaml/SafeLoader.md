# Yaml.SafeLoader for speed up the load.
Since `yaml.load` allows to evaluate an expression with `!!`, it brings lots of potential security issues. 
Therefore we have `yaml.safe_load` to mitigate this issue but it's written in pure python and it's much slower then `yaml.load` written in C. 
So, to have load speed of `yaml.load` and protection of `yaml.safe_load` use `yaml.SafeLoader` as loader in `yaml.load`.

```python
import yaml

yaml.load(...., loader=yaml.SafeLoader)
```
