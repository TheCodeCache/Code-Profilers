# Bash Profiling  

We need to follow these 2 steps to profile a bash script:  
1. locate and open this file `/etc/bash.bashrc`  
2. Add this at the beginning of `/etc/bash.bashrc`  
 (or wherever you'd like to begin a trace in any Bash script):  
 ```
 PS4='+ $(date "+%s.%N")\011 '
 exec 3>&2 2>/tmp/bashstart.$$.log
 set -x
 ```
3. Add this at the end of `~/.bashrc`  
 (or at the end of the section of any Bash script you'd like tracing to stop)  
 ```
 set +x
 exec 2>&3 3>&-
 ```

To profile an existing script:  
  PS4='+ $(date "+%s.%N ($LINENO) ")' bash -x <script_name.sh>  

Reference(s):  
1. https://stackoverflow.com/a/5015179/6842300  
2. https://stackoverflow.com/a/4338046/6842300  
  
  
