## Core dump instructions

In order to dump the core without having to run the program via the debugger, tell the system where to dump the core and turn on unlimited core files. 

Tell the system to use unlimited core files:
```terminal
ulimit -c unlimited 
```

check the current location where the core is dumped:
```
cat /proc/sys/kernel/core_pattern 
```
If it does not show "./core" update the core_pattern file 

```
sudo su 
echo "./core" > /proc/sys/kernel/core_pattern 
exit
```

Build the program in debug mode: 
```
cmake -DCMAKE_BUILD_TYPE=Debug .. 
```

Run the program as normal and when the program has crashed with a core dump there should be a file located named 'core' 
Open the core dump with gdb: 

```
gdb ./executable ./core 
```

This should show where the program crashed.

Do not forget to switch back to Release mode:
```
cmake -DCMAKE_BUILD_TYPE=Release ..
```
