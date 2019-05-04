# Resource:
Give me 15 mininutes => change your view GDB
https://www.youtube.com/watch?v=PorfLSr3DDI

Tips:
https://github.com/hellogcc/100-gdb-tips

10 minutes to Learn:
https://blog.csdn.net/liigo/article/details/582231

# GDB Dashboard
> ::start:: http://tuxdiary.com/2015/09/13/gdb-dashboard/
>
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
tty
# (e.g. */dev/ttys001*, the name may be different for a variety of reasons);
```
4. issue the command:
```shell
dashboard -output */dev/ttys001* 
# to redirect the dashboard output to the newly created terminal;
```
5. debug as usual.

# GDBGUI
https://www.gdbgui.com/installation/

benifit: scroll (gdb dashboard hasn't) => show 

1. start gdbgui server in console
```
gdbgui -r
# remote
```
2. click [load binary] button with the correct compiled binary(obj)

3. set break point

4. press 
- 'r' run, 
- 'c' continue, 
- 'n' step over, 
- 's' step into, 
- 'u' step out

5. click 'show filesystem' => tree code files, 
'fetch assembly' => show assembly code biside source code, 
'reload file' => fresh occurs errors


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
