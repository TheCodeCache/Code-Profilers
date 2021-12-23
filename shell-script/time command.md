# `time` cmd in unix:

```shell
$ time aws s3 cp --recursive --quiet . s3://test_bucket/test_smallfiles/
```
Outcome:  
```
real    19m59.551s
user    7m6.772s
sys     1m31.336s
```

The `time` command returns the `real` or `wall clock` time the `aws s3 cp` took to complete.  
Based on the real output value from the time command,  
the example took `20 minutes` to complete the copy of all directories and the files in those directories.  

**Reference:**  
1. https://aws.amazon.com/blogs/apn/getting-the-most-out-of-the-amazon-s3-cli/

