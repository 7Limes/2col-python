# 2col

A minimal stack oriented language where each line contains only 2 columns.

## Running
Run from command line:
```
python twocol.py [filename] (-d)
```

Run from python script:
```py
from twocol import TwocolInterpreter
tc = TwocolInterpreter()
tc.run('script.2c')
```

## Commands:
Each command is formatted as `[command] [value]`

s[0] refers to the first value of the stack (the one on top), and s[1] refers to the second value.

- `! [value]` -- print value to console
- `! .[value]` -- print ascii character equivalent of value to console
- `# [value]` -- push value to stack
- `&` -- pop s[0] from stack
- `+` -- pop first 2 values from stack and push their sum to the stack
- `-` -- pop first 2 values from stack and push s[1] - s[0] to the stack
- `*` -- pop first 2 values from stack and push their product to the stack
- `/` -- pop first 2 values from stack and push s[1] / s[0] to the stack
- `%` -- pop first 2 values from stack and push s[1] % s[0] to the stack
- `?` -- skip the next line if s[0] == s[1]
- `? [value]` -- skip the next line if s[0] == value
- `^ [value]` -- jump to label that is named value
- `@ [value]` -- label a line
- `$` -- swap s[0] and s[1]
- `$ [value]` -- swap s[0] and s[value]
- `~` -- comment (must be first character)

## Value Commands
Value commands are special characters that are used in [value] that will insert different things into an expression.

- `p` -- get and pop the top value from the stack
- `c` -- copy the top value from the stack without popping
- `i` -- get integer input from user

### Extra Notes
Labels are initialized before execution, so jumping downward to labels also works. For example:

```
# 0

? 0
^ 1
~ this 'a' is never printed
! .97

@ 1
! .101
```
