# Gnulib buildTool
This build Tool provides a script to make Gnulib available on its own.  
If you want to use gnulib, autoconf is required. However, it was quite a barrier to users using other build systems. Because, gnulib and autoconf is were deeply integrated by Autoconf and m4 macro.  
So, I solved this problem by  modify the sample that was attached to gnulib.   

## Build Requirements
- POSIX Environment (POSIX compliance shell, POSIX command)
- Autotools
## Build Step
1. Add the following environment variables to the shell configuration file:
~~~
export GNULIB_SRCDIR=<dir>
~~~

2. Set build module, Run the source code generator.
~~~
./autogen.sh <module1> <module2> <moduleN>...
~~~

    example: Build libc provided by gnulib.
~~~
./autogen.sh assert-h ctype-h errno-h float-h inttypes-h limits-h-h locale-h \
math-h signal-h-h stdarg-h stdbit-h stdckdint-h stdcountof-h-h stddef-h stdint-h \
stdio-h stdlib-h string-h threads-h time-h uchar-h wchar-h wctype-h arpa_inet-h \
dirent-h endian-h fcntl-h fnmatch-h glob-h iconv-h langinfo-h netdb-h net_if-h \
netinet_in-h poll-h pthread-h regex-h sched-h search-h spawn-h strings-h sys_msg-h \
sys_resource-h sys_select-h sys_sem-h sys_shm-h sys_socket-h sys_stat-h sys_time-h \
sys_times-h sys_types-h sys_uio-h sys_un-h sys_utsname-h sys_wait-h termios-h unistd-h
~~~

3. build
~~~
./configure && make -j$(nproc)
~~~

## Build File Clean
~~~
./autoclean.sh
~~~

## HOW TO USE
The header file and static library are found in `./lib` directiry.

## LICNESE
This repository licensed under CC0.
