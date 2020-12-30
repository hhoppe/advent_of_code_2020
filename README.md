# Advent of code 2020

<[**Open the notebook using Colab**](https://colab.research.google.com/github/hhoppe/advent_of_code_2020/blob/main/advent_of_code_2020.ipynb)>

Jupyter [notebook](https://github.com/hhoppe/advent_of_code_2020/blob/main/advent_of_code_2020.ipynb) by [Hugues Hoppe](http://hhoppe.com/); December 2020.

I participated in the 25-day [Advent of Code](https://adventofcode.com/) for the first time this year, thanks to encouragement from colleagues, especially [Sascha Häberling](https://github.com/shaeberling).  It was great fun and provided a nice opportunity to learn more advanced Python.

In the event, many people compete to solve the puzzles as quickly as possible --- see the impressive times on the [leaderboard](https://adventofcode.com/2020/leaderboard).
My approach was much more casual, although I did aim to finish the puzzle each evening.

Later, I went back to explore more **polished and efficient solutions**.
Can the code be expressed more succinctly?
What is the fastest algorithm given the constraints of interpreted Python?
Along the way, I discovered the [`numba`](https://numba.pydata.org/) package which can JIT-compile native code to overcome bottlenecks;
is it practical for these problems?  Yes, it can help greatly!
