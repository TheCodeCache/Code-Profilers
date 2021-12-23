# Profiling block of code in Shell-Script - 

**Approach - 1**:  

Put the block of code in a temp function and time it like below - 

```shell
main () {
 echo running ...
}

# stuff ...

# calling the function at the very end of the script
time main
```

**Approach - 2:**  

It's the most general appraoch and is the most natural as well - 
```shell
start=`date +%s`
stuff
end=`date +%s`

runtime=$((end-start))
```

**Approach - 3:**  

We can directly run `time` cmd with `shell-script` itself - 

```shell
$ time hello_world.sh
```

**Approach - 4:**  

We can also use the Bash shell’s `TIMEFORMAT` combined with the time command,  
to calculate the exact time spent on a block of commands with milliseconds precision  

```shell
TIMEFORMAT='It took %R seconds.'
time {
sleep 5 # add stuffs here, simulating with sleep cmd
sleep 7 $ add stuffs here, simulating with sleep cmd
}
```

**Approach - 5:**  

We can make use of a linux variable called `SECONDS`, it's an `internal variable` in Linux.  

`SECONDS` returns a count of the number of (whole) seconds the shell has been running.  
In the case of a shell script, this is the time that the script itself, not the shell which called it, has been running.  
If we change the value of SECONDS to another integer, it will keep counting from there

```shell
# Reset BASH time counter
SECONDS=0
    # 
    # do stuff
    # 
ELAPSED="Elapsed: $(($SECONDS / 3600))hrs $((($SECONDS / 60) % 60))min $(($SECONDS % 60))sec"
```

The last approach is probably the best approach to profile a block of code in shell-script.  

**Reference:**  
1. https://unix.stackexchange.com/a/340156
2. https://www.baeldung.com/linux/bash-calculate-time-elapsed#using-bash-shells-timeformat

