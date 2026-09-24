# Python Learning Notebooks

A collection of 15 Jupyter notebooks for learning Python through short examples, exercises, and interactive demos. Topics include basic syntax, strings, collections, Boolean values, comparison operators, conditional statements, loops, and file handling.

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
| [Comparison operators](notebooks/python-operators.ipynb) | The six comparison operators, chained comparisons, logical conditions, string comparisons, equality versus identity, and floating-point comparisons; includes practice exercises, hints, and solutions. |
| [Conditional statements](notebooks/python-statements.ipynb) | `if`, `elif`, and `else`; indentation, truthiness, branch order, and case-sensitive string comparisons, with practice prompts. |
| [Loops](notebooks/python-loop.ipynb) | `for` and `while` loops, running totals, tuple unpacking, dictionary iteration, loop `else`, and control with `pass`, `continue`, and `break`. |
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
- **Expected errors:** The strings notebook demonstrates an invalid attempt to modify a string. The file-handling notebook demonstrates opening a missing file and exclusive creation of an existing file. The tuples notebook also demonstrates `index()` raising `ValueError` for a missing value. These cells intentionally raise errors; inspect the explanation and continue with the next cell. Run All may stop at an unhandled error.
- **Comparison practice:** Predict the example results before running them, then replace the exercise placeholders with your own conditions. Expand the hints and solutions after attempting the exercises. Expected errors in this notebook are caught so all cells can run in order.
- **Statements and loops:** Change inputs to explore different branches and iterations. The loops notebook reuses variables such as `my_list`; rerun the relevant setup cell before revisiting an example. When experimenting with `while`, keep an update or exit condition that lets the loop finish; interrupt the kernel if it runs indefinitely.
- **Interactive demos:** Run the setup cell to display the widgets. Use the emoji-rain demo's stop control to end the animation and the tic-tac-toe reset control to start a new game.

## Contributing

This repository is for personal learning. Corrections, clearer explanations, and additional exercises are welcome through issues or pull requests. Keep examples focused and include any setup instructions they require.

## License

Licensed under the [MIT License](LICENSE). Copyright (c) 2024 Kanwal Preet Singh.
