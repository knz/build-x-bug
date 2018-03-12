
Base execution:

```
$ go build
$ ./base-x-val
baseVal

$ go build -ldflags '-X github.com/knz/build-x-bug/src.TheVal=override
$ ./base-x-val
override
```

All good!

Bug:

```
$ cd /tmp
$ ln -s $GOPATH/src/github.com/knz/build-x-val
$ cd build-x-val
$ go build -ldflags '-X github.com/knz/build-x-bug/src.TheVal=override
$ ./base-x-val
baseVal
```

Bad!

