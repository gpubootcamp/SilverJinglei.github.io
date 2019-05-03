# Resource:
Give me 15 mininutes => change your view GDB
https://www.youtube.com/watch?v=PorfLSr3DDI

Tips:
https://github.com/hellogcc/100-gdb-tips

10 minutes to Learn:
https://blog.csdn.net/liigo/article/details/582231

# GDB Dashboard
> ::start:: http://tuxdiary.com/2015/09/13/gdb-dashboard/
> https://github.com/cyrus-and/gdb-dashboard

> official github miss the detail
Steps:
1. install tmux
tmux => sperate output

cmd tutorial:
https://www.cnblogs.com/wangqiguo/p/8905081.html

2. start GDB in one terminal;
3. open another terminal (e.g. tmux pane) and get its TTY:
```shell
tty command
(e.g. */dev/ttys001*, the name may be different for a variety of reasons);
```
4. issue the command:
```
dashboard -output */dev/ttys001* 
// to redirect the dashboard output to the newly created terminal;
```
5. debug as usual.


# other
https://www.youtube.com/watch?v=bWH-nL7v5F4

Compile for debugging
```c
gcc -Wall -g program.c
```
Preserve identifiers and symbols

Start GDB
```c
gdb a.out
```

Optionally start with CLAs
```
gdb --args a.out arg1 arg2
```
