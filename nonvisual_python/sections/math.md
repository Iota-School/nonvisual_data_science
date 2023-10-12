

# A Little Math

At this point, you should have NVDA running, and you should have an active Anaconda Prompt window open. You should also have typed `ipython` to start a running Python interpreter. After typing `ipython`, you should hear the following output from NVDA:

```
Python 3.8.13 (default, Oct  6 2023, 13:32:16) 
Type 'copyright', 'credits' or 'license' for more information
IPython 8.12.3 -- An enhanced Interactive Python. Type '?' for he
```

Now let's try a little math. Enter the following:

```python
3 + 3
```

That's three, a space, a plus sign, a space, and a three. 

Once you have typed this, hit enter. You should hear:

```
Out[1]: 6

In [2]: 
```

The output you're hearing consists of three lines. The first is our result, and appars as below:

```
Out[1]: 6
```

Our input was `3 + 3`, and our result was `6`. The beginning of this line also includes `Out[1]`, meaning that this is the first output of this session.

The second line of this output is blank. NVDA will usually represent these blank lines with the work `blank`.

The third line starts with `In [2]: `, meaning that IPython is again waiting for our input.

As you continue to type lines of code into IPython, you'll notice that input and output are grouped together, and that a blank line separates these groups. We'll soon go into detail on navigating back through your output, but for now, let's do a little more math.

## More Math

Enter the following lines as input:

```
10 - 4
```

```
5 * 5
```

```
44 / 4
```

In Python, we use a minus (`-`)sign (or hyphen) for subtraction, an asterisk or star (`*`) for multiplication, and a forward slash (`/`) for division. There are other mathematical operators, but we'll stick to these for now.


