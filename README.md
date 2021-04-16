## Reproduce
Running the nodejs_binary target
```shell script
export TLD=.com
bazel run //home:bin
...
> TLD .com
```

Running the nodejs_image with a bound Make variable. i.e $(VAR)
```shell script
export TLD=.com
bazel run //home:image_bound
...
>/app/home/image_bound.binary: line 94: TLD: command not found
>TLD 
```

Running the nodejs_image with an unbound Make variable. i.e $VAR
```shell script
export TLD=.com
bazel run //home:image_unbound
...
>/app/home/image_unbound.binary: line 94: TLD: unbound variable
```