# a collection of the classic nano program

## convert integer to binary
```
test = 100
bin20 = lambda x: ''.join(reversed( [str((x >> i)&1) for x in range(20)] ))
bin20(test)
```
