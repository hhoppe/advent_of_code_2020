# Advent of code 2020

Jupyter [notebook](https://github.com/hhoppe/advent_of_code_2020/blob/main/advent_of_code_2020.ipynb) by [Hugues Hoppe](https://hhoppe.com/); December 2020.

I participated in the 25-day [Advent of Code](https://adventofcode.com/) for the first time this year, thanks to encouragement from colleagues, especially [Sascha Häberling](https://github.com/shaeberling).  It was great fun and provided a nice opportunity to learn more advanced Python.

In the event, many people compete to solve the puzzles as quickly as possible --- see the impressive times on the [leaderboard](https://adventofcode.com/2020/leaderboard).
My approach was much more casual, although I did aim to finish the puzzle each evening.

Later, I went back to explore more **polished and efficient solutions**.
Can the code be expressed more succinctly?
What is the fastest algorithm given the constraints of interpreted Python?
Along the way, I discovered the [`numba`](https://numba.pydata.org/) package which can JIT-compile bottleneck functions to native code;
is it practical for these problems?  Yes, it can help greatly!

This notebook is organized such that each day is self-contained and can be run on its own after the preamble.

- The [**preamble**](#preamble) readies the inputs and answers for the puzzles.  No custom shortcut functions are introduced (other than `check_eq`) so the puzzle code solutions are easily recognizable.

- For **each day**, the first notebook cell defines a `puzzle` object:

  ```
    puzzle = advent.puzzle(day=1)
  ```
  The puzzle input string is automatically read into the attribute `puzzle.input`.
  This input string is unique to each Advent participant.
  By default, the notebook uses [my input data](https://github.com/hhoppe/advent_of_code_2020/tree/main/data) stored on GitHub,
  but the variable `INPUT_DATA_PATH_OR_URL_FORMAT` can refer to any directory or URL.
  Similarly, the (per-user) puzzle answers are read from my JSON [file](https://github.com/hhoppe/advent_of_code_2020/blob/main/data/answers.json) specified in `ANSWERS_PATH_OR_URL`.

  For each of the two puzzle parts, a function (e.g. `process1`) takes an input string and returns a string or integer answer.
  Using calls like the following, we time the execution of each function and verify the answers:
  ```
    puzzle.verify(part=1, func=process1)
    puzzle.verify(part=2, func=process2)
  ```

- At the end of the notebook, a table summarizes [**timing**](#timings) results.

Some **conclusions**:

- A Jupyter/IPython notebook is a great environment for exploration.
- The notebook conveniently bundles descriptions, notes, code, small test inputs, and results.
- Initially I stored puzzle inputs within the notebook itself, but this introduces clutter and runs inefficiently.
- The cloud-based CPU kernel/runtime provided by Colab works nicely.
- With the [`numba`](https://numba.pydata.org/) library (for days [11](#day11), [15](#day15), and [23](#day23)), all of this year's puzzles can be solved in 1 second or less.
- Remarkably, the total execution time across all 25 puzzles is under 4 s.
