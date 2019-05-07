# Resource:
Give me 15 mininutes => change your view GDB
https://www.youtube.com/watch?v=PorfLSr3DDI

Tips:
https://github.com/hellogcc/100-gdb-tips

10 minutes to Learn:
https://blog.csdn.net/liigo/article/details/582231

# GDB TUI
> https://blog.csdn.net/xu415/article/details/19021759

> http://beej.us/guide/bggdb/

> http://www.deansys.com/doc/gdbDebugging/gdb_23.html
Cool show source/assembly/register window with scroll!


# GDB Dashboard
> ::start:: http://tuxdiary.com/2015/09/13/gdb-dashboard/
>
> https://github.com/cyrus-and/gdb-dashboard

> official github miss the detail
Steps:
1. install tmux
tmux => sperate output
window rename: ctrl + B + <

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

# GDB SERVER
> https://www.cnblogs.com/Dennis-mi/articles/5018745.html

> https://blog.csdn.net/rebirthme/article/details/78874229

> https://www.jb51.net/article/130573.htm

> https://sourceware.org/gdb/onlinedocs/gdb/Server.html
* 运行gdbserver以连接到远程GDB的系统也可以在 本地运行 GDB！ 
* gdbserver比GDB本身要小得多, 它比所有GDB都更容易移植，更快地启动gdbserver
* 实时系统开发代码，实时操作中涉及的权衡使得在另一个系统上进行尽可能多的开发工作变得更加方便，例如通过交叉编译。您可以使用gdbserver类似的选项进行调试。

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
