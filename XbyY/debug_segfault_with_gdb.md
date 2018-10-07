# Problem statement

## Segfault

When programming in C or C++, we often have to play with pointers directly, or indirectly (using std::vector for example), and we can find segfaults when executing our programs.

Segfaults are bugs that appear **only** at runtime, and can be tricky because it depends on the behaviour of the program, which can change from one execution to another (cf GUI programs).

## Category

Debugging

## Solution

Let's say you built your program as `at.out`, and when you ran it, you got a nice "Segfault (core dump)".

We'll launch GDB with this command : `gdb a.out`

Then, type `r` and press `RETURN`, your program will start. Now lets wait for the segfault...

When the segfault appears, get back to your terminal, and type `bt`, it will display the backtrace of the program. You'll have to find the line in your code which "launch" the segfault. Note the filename as well.

For example it could be : `directory/file.cpp:55 [...]`, we'll need the "file.cpp:55" part.

Now, we'll re-run the program :

```shell
gdb a.out
# adding a break point
> b file.cpp:55
# running the program
> r
# waiting for breakpoint to be reach
> display a_variable_name
```

The display part is really important, before continuing to execute the program. I usually do multiple display commands, to display all the variable I am using at this point in the program. When it's done, I just type `c`, then I press `RETURN`, and I watch the variables being displayed when GDB reach again the breakpoint, and I continue to type `c`, then press `RETURN` to wait for the segfault to come again.

When the segfault appears, I just look at all the data displayed by GDB, and very often, I'm just doing a `my_array[i]` with i >= the length of the array.

With this method, you've everything you need to track your segfaults, happy debugging !
