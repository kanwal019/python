# Python Learning Notebooks

A collection of 16 Jupyter notebooks for learning Python through short examples, exercises, and interactive demos. Topics include basic syntax, strings, collections, Boolean values, comparison operators, conditional statements, loops, functions, variable scope, and file handling.

## Notebook Guide

Start with the introduction, then explore the topics below. All notebooks are in [`notebooks/`](notebooks/).

| Notebook | What it covers |
| --- | --- |
| [First steps](notebooks/python-start.ipynb) | Basic calculations, indentation, types, and Python syntax. |
| [Strings](notebooks/python-strings.ipynb) | Indexing, slicing, immutability, string methods, and formatting with `format()` and f-strings. |
| [Lists](notebooks/python-lists.ipynb) | Creating and modifying lists, slicing, sorting, enumeration, comprehensions, nested lists, and shallow copying. |
| [Tuples](notebooks/python-tuples.ipynb) | Immutable sequences, slicing, concatenation, repetition, tuple methods, starred unpacking, and nesting. |
| [Sets](notebooks/python-sets.ipynb) | Creating sets, adding items, uniqueness, and removing duplicate characters. |
| [Dictionaries](notebooks/python-dictionaries.ipynb) | Creating, reading, updating, and deleting entries; dictionary views, copying, iteration, nesting, comprehensions, frequency counting, and merging. |
| [Booleans](notebooks/python-booleans.ipynb) | Introductory examples of `True`, `False`, equality comparisons, and `or`. |
| [Operators and iteration tools](notebooks/python-operators.ipynb) | Comparisons, logical and membership operators, equality versus identity, floating-point comparisons, `range()`, `enumerate()`, `zip()`, `min()`, `max()`, random values, and user input; includes practice exercises, hints, and solutions. |
| [Conditional statements](notebooks/python-statements.ipynb) | `if`, `elif`, and `else`; indentation, truthiness, branch order, and case-sensitive string comparisons, with practice prompts. |
| [Loops](notebooks/python-loop.ipynb) | `for` and `while` loops, running totals, tuple unpacking, dictionary iteration, loop `else`, and control with `pass`, `continue`, and `break`. |
| [Functions](notebooks/python-functions.ipynb) | Definitions, defaults, printing versus returning, argument types and `+`, even-number checks and filtering, tuple unpacking, a guessing game, `*args`, `**kwargs`, alternating-case string exercises, `map()`, `filter()`, lambda expressions, nested functions, LEGB scope, `global`, twelve additional function exercises, a bonus letter-pattern exercise, and homework on sphere volume, inclusive ranges, letter-case counts, unique elements, multiplication, palindromes, and pangrams. |
| [File handling](notebooks/python-files.ipynb) | Reading, writing, appending, file positions, context managers, and file modes. |
| [Practice exercises](notebooks/python-fun.ipynb) | Loops with strings and a list-based to-do example. |
| [Tic-tac-toe](notebooks/python-tic-tac-toe.ipynb) | An interactive widget-based game with winner checks and a reset control. |
| [Emoji rain](notebooks/python-emoji-rain.ipynb) | An animated widget demo using random values, timing, and a background thread. |
| [Simple example](notebooks/example.ipynb) | Printing a greeting and a fruit list. |

## Repository Layout

```text
notebooks/        Jupyter notebooks for lessons, exercises, and demos
files/            Sample text files used by the file-handling notebook
example.py        Standalone greeting and list example
requirements.txt  Existing package notes (see setup below)
LICENSE           MIT license
```

## Setup

Use Python 3 with pip. Run these commands from the repository root in PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install jupyterlab ipywidgets
```

JupyterLab provides the notebook interface. `ipywidgets` supports the tic-tac-toe and emoji-rain demos. The basic lessons primarily use Python's built-in features and standard library.

The current [`requirements.txt`](requirements.txt) contains `import numpy`, `import pandas`, and `import requests` rather than pip requirement entries, so it cannot currently be used with `pip install -r requirements.txt`. If you want these additional packages for experimentation, install them directly:

```powershell
python -m pip install numpy pandas requests
```

## Running the Examples

With the virtual environment active, start JupyterLab from the repository root:

```powershell
jupyter lab
```

Open a notebook in `notebooks/` and select the Python kernel associated with `.venv`. Run cells from top to bottom because later examples often depend on variables created or modified earlier. Restart the kernel when you want to begin with a clean state.

You can also open the notebooks in VS Code with the Python and Jupyter extensions and select `.venv` as the notebook kernel.

To run the standalone example from the repository root:

```powershell
python example.py
```

### Notes for Specific Notebooks

- **File handling:** Relative paths such as `../files/temp.txt` assume the kernel's working directory is `notebooks/`. Check it with `%pwd` and, if it is the repository root, use `%cd notebooks` before running the examples. Some cells create, overwrite, or append to files in `files/`.
- **Expected errors:** The strings notebook demonstrates an invalid attempt to modify a string. The file-handling notebook demonstrates opening a missing file and exclusive creation of an existing file. The tuples notebook also demonstrates `index()` raising `ValueError` for a missing value. The functions notebook demonstrates `TypeError` when `+` is used with unsupported argument types, such as dictionaries or an integer and a string, and when too many arguments are passed to the fixed-parameter version of `my_func`. These cells intentionally raise errors; inspect the explanation and continue with the next cell. Run All may stop at an unhandled error.
- **Operators and iteration tools:** Predict the comparison results before running them, then try changing the completed practice conditions. Expand the hints and solutions after attempting the exercises. Run the later examples in order to prepare the lists used by `enumerate()`, `zip()`, membership checks, and random shuffling. The final `input()` cell waits for a whole number such as `42`; blank or non-integer input raises `ValueError`.
- **Statements and loops:** Change inputs to explore different branches and iterations. The loops notebook reuses variables such as `my_list`; rerun the relevant setup cell before revisiting an example. When experimenting with `while`, keep an update or exit condition that lets the loop finish; interrupt the kernel if it runs indefinitely.
- **Functions:** Run the definitions before their calls. Later cells redefine `print_hello` to accept a default name and change `check_even_list` from returning a Boolean to returning a list of even numbers. Several versions of `my_func` demonstrate fixed parameters, `*args`, `**kwargs`, and the final filtering and string exercises; each definition replaces the previous one. Rerun the corresponding definition when revisiting an earlier example. Compare the value returned by `add_numbers` with the `None` returned by `print_item`. The guessing game waits for input: enter `0`, `1`, or `2` at the prompt.
- **Interactive demos:** Run the setup cell to display the widgets. Use the emoji-rain demo's stop control to end the animation and the tic-tac-toe reset control to start a new game.
- **Map, filter, and lambdas:** The map and filter section transforms numbers and strings with `map()`, keeps matching numbers with `filter()`, and uses short lambda expressions as callbacks. Both built-ins return iterators; the examples consume them with a loop or `list()`. Run the section in order: `my_nums` changes from five numbers to six, `check_even` is redefined, and a lambda replaces the named `square` function. The section ends by reversing each name's characters while preserving the order of the names.
- **Nested statements and scope:** Follow the LEGB lookup order: local, enclosing, global, then built-in. The examples demonstrate shadowing, case-sensitive names (`X` versus `x`), and updating a module-level variable with `global`. The explanations also distinguish reading an enclosing name from rebinding it with `nonlocal`. Run the cells in order because `greet`, `func`, and `x` are redefined; the later `func()` takes no arguments and changes the global `x` from `50` to `100` when called.
- **Function practice:** After the scope examples, the functions notebook includes twelve exercises and worked solutions, plus a bonus letter-pattern exercise, followed by Functions and Methods Homework. Topics include numeric conditions, string transformations, adjacent list values, summing selected values, ordered subsequences, and counting primes. Try each prompt before running its solution, then compare the sample calls with your own inputs. `animal_crackers` expects a two-word string and ignores letter case; `blackjack` expects three integers between `1` and `11`; `summer_69` assumes each `6` is followed by a `9`. Compare `count_primes` and `count_primes_v2` on the same integer inputs; both return `0` for values below `2`. The bonus `print_big` function supports lowercase letters `a` through `e` and prints a message for unsupported input.

### Function Practice Guide

These exercises are in [`python-functions.ipynb`](notebooks/python-functions.ipynb), after the scope examples.

| Function | Practice topic |
| --- | --- |
| `lesser_of_two_evens` | Return the smaller number when both are even, otherwise the larger. |
| `animal_crackers` | Compare the first letters of two words without case sensitivity. |
| `makes_twenty` | Check whether either number or their sum equals `20`. |
| `old_macdonald` | Capitalize the first and fourth letters of a name, with a message for names shorter than four characters. |
| `master_yoda` | Reverse word order using splitting, slicing, and joining. |
| `almost_there` | Use absolute differences to check whether a number is within `10` of `100` or `200`. |
| `has_33` | Scan a list for adjacent `3` values. |
| `paper_doll` | Repeat each character three times. |
| `blackjack` | Practice conditional scoring with a total of `21`, an adjustment for `11`, and a `BUST` result. |
| `summer_69` | Sum list values while skipping each section from `6` through the next `9`, inclusive. |
| `spy_game` | Check for `0`, `0`, and `7` in order, allowing other values between them. |
| `count_primes`, `count_primes_v2` | Count primes up to and including an integer using two approaches: division by previously found primes and trial division up to the candidate's square root. |
| `print_big` (bonus) | Print a five-row star pattern for a lowercase letter from `a` through `e`. |

### Functions and Methods Homework

The final section of [`python-functions.ipynb`](notebooks/python-functions.ipynb) adds these exercises:

| Function | Practice topic |
| --- | --- |
| `vol` | Return a sphere's volume from its radius using `(4/3) * pi * rad**3`. |
| `ran_check` | Print whether an integer belongs to the inclusive range from `low` to `high`. |
| `ran_check_bool` | Return the same inclusive integer-range check as a Boolean. |
| `up_low` | Print the original string and its uppercase and lowercase letter counts using `isupper()` and `islower()`. |
| `unique_list` | Return distinct hashable list elements using `list(set(lst))`; input order is not preserved. |
| `multiply` | Return the product of all numbers in a list, starting from `1`. |
| `palindrome` | Check whether a string reads the same backward after removing spaces and converting to lowercase. |
| `ispangram` | Check whether a string contains every letter of an alphabet, defaulting to the lowercase English alphabet. |

Use integer bounds with `low <= high` for the range exercises. Compare `ran_check`, which prints a message and returns `None`, with `ran_check_bool`, which returns `True` or `False`.

`up_low` ignores characters with neither uppercase nor lowercase status, such as digits, spaces, and punctuation. It scans the string once in O(n) time with O(1) extra space for the counters. The sample `Hello Mr. Rogers, how are you this fine Tuesday?` produces 4 uppercase and 33 lowercase letters.

`unique_list` requires hashable elements, such as numbers or strings. Its set conversion removes duplicates but does not guarantee the order of first occurrence, despite the sample call's comment. `multiply([1, 2, 3, -4])` returns `-24`; an empty list returns `1`.

`palindrome` ignores literal spaces and letter case, so `palindrome('Nurses run')` returns `True`; punctuation and other whitespace remain significant. `ispangram` lowercases the input and checks for every character in `alphabet`. The default recognizes `The quick brown fox jumps over the lazy dog` as a pangram. Run the cell containing `import string` and the function definition before the sample calls.

## Contributing

This repository is for personal learning. Corrections, clearer explanations, and additional exercises are welcome through issues or pull requests. Keep examples focused and include any setup instructions they require.

## License

Licensed under the [MIT License](LICENSE). Copyright (c) 2024-2026 Kanwal Preet Singh.
