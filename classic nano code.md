# a collection of the classic nano program

## convert integer to binary
```
test = 100
bin20 = lambda x: ''.join(reversed( [str((x >> i)&1) for x in range(20)] ))
bin20(test)
``` 
*  note 1, the usage of lambda function.
*  note 2, the usage of ''.join() function.
*  note 3, have to cast (x >> i)&1 to str in order to get the last digit.
*  note 4, the usage of reversed(). the return value is the reversed input list. we cannot use the [].reverse() method here since its return value is None. 
*  note 5, the str itself cannot be feed into reversed() since it is immutable. we need to cast it into list first.
