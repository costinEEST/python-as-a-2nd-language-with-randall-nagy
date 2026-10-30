# The Python Interpreter

Python includes an interactive interpreter, often called the **REPL**. REPL
stands for **Read-Eval-Print Loop**: Python reads a command, evaluates it,
prints the result (when there is one), and waits for the next command.

## Starting the interpreter

From a terminal, run:

```console
$ python3
Python 3.15.0 ...
>>>
```

- `python3` starts the Python 3 interpreter.
- The version banner identifies the Python version and the platform on which it
  was built. Its exact contents differ between computers.
- `>>>` is the primary Python prompt. It means that the interpreter is ready
  for Python code. Do not type the prompt itself when following the examples.

## Using the help system

At the Python prompt, call the built-in `help()` function:

```pycon
>>> help()
Welcome to Python's help utility!
help>
```

`help()` opens Python's interactive help utility. The prompt changes from
`>>>` to `help>` because commands entered here are help topics, not Python
expressions.

To list the available documentation topics, enter `topics`:

```text
help> topics
ASSERTION    ASSIGNMENT    EXPRESSIONS    FUNCTIONS    ...
```

To open a topic, enter its name exactly as shown in the list:

```text
help> FRAMES
```

Help-topic names can be case-sensitive. For example, `frames` may not find the
topic while `FRAMES` does.

To leave the help utility, enter `quit` without parentheses:

```text
help> quit
You are now leaving help and returning to the Python interpreter.
>>>
```

Inside the help utility, `quit` is a command. Writing `quit()` asks for a topic
literally named `quit()`, which does not exist. Once the `>>>` prompt returns,
the input is Python code again.

## Inspecting the current namespace

```pycon
>>> dir()
['__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__']
```

With no argument, the built-in `dir()` function lists the names currently
defined in the active namespace. A new interpreter already contains several
special names. Names surrounded by double underscores are commonly called
*dunder* names (short for “double underscore”). They support Python's internal
object and module behavior.

The exact list can vary by Python version and environment.

## Creating and inspecting a variable

```pycon
>>> my_var = "Costi"
```

The assignment operator `=` binds the name `my_var` to the string object
`"Costi"`. Assignment changes the interpreter's state, but it does not display
a result.

```pycon
>>> dir(my_var)
['__add__', '__class__', ..., 'capitalize', 'lower', 'replace', ..., 'upper']
```

When given an object, `dir(object)` lists the attributes and methods available
on that object. Because `my_var` currently refers to a string, the list includes
string methods such as `lower()`, `replace()`, and `upper()`, along with special
dunder methods. The list above is shortened because its precise contents can
change between Python versions.

## Asking for help about an object

The original session tried this:

```pycon
>>> help(my_var)
No Python documentation found for 'Costi'.
```

This result is slightly surprising. Because `my_var` contains the string
`"Costi"`, `help()` interprets its value as the **name of a help topic** and
looks for documentation about `Costi`.

To see documentation for the string type, pass the type itself instead:

```pycon
>>> help(str)
Help on class str in module builtins:
...
```

For help with one particular string method, pass that method without calling
it:

```pycon
>>> help(str.upper)
Help on method_descriptor:
...
```

`str.upper` refers to the method so that `help()` can inspect it. Writing
`str.upper()` would attempt to call the method and is not appropriate here.

## Checking and changing types

```pycon
>>> type(my_var)
<class 'str'>
```

The built-in `type()` function returns an object's type. At this point,
`my_var` refers to a string, so its type is `str`.

```pycon
>>> my_var = 2
>>> type(my_var)
<class 'int'>
```

The name is reassigned to the integer `2`, so `type(my_var)` now returns
`int`. Python names are not permanently restricted to one type.

```pycon
>>> my_var = 2.1
>>> type(my_var)
<class 'float'>
```

The name is reassigned again, this time to the floating-point number `2.1`.
Its type is therefore `float`.

## Leaving the interpreter

```pycon
>>> quit()
```

At the regular Python prompt, `quit()` exits the interpreter and returns to the
terminal. Unlike the `quit` command inside `help>`, parentheses are appropriate
here because this input is evaluated as Python code.

You can also send an end-of-file signal: press **Control-D** on macOS or Linux,
or **Control-Z** followed by **Enter** on Windows.
