## Regular expressions in python
- provided by the ```re``` module in python
- raw strings should be provided like: ```r'strings'```

#### ```re.match(pattern, string, flags = 0)```

- success: match object
- failure: none
- match object methods:
  - group(num = 0) -> returns the entire match or a specific subgroup
  - groups() -> returns subgroups in a tuple

#### Search and replace ```re.sub(pattern, replaement, string, max=0)```

- replace all occurrences of the  pattern with replacement unless max is provided

#### flags

- ```re.I```: case-insensitive
- ```re.L```:
- ```re.M```:
- ```re.S```:
- ```re.U```:
- ```re.X```
#### References

-[](https://www.tutorialspoint.com/python/python_reg_expressions.htm)
