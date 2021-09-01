## Golang
### strings
Strings are unchangeable

```go
s := "test"
println(s[0]) 
s[0] = "R" // WRONG; this code doesn't work! (not compile)
s = "R"+s[1:] // OK
println(s)
```

### difference between sync.Mutex and sync.RWMutex
sync.Mutex has 2 methods for use:
```go
mu := &sync.Mutex{}

// locks for each goroutine (for read and for write)
mu.Lock()
mu.Unlock()
```

sync.RWMutex has 4 methods:
```go
mu := &sync.Mutex{}

// locks for each goroutine (for read and for write)
mu.Lock()
mu.Unlock()

// allow goroutines to read 
mu.RLock()
mu.RUnlock()
```
As a mutex, the lock occurs only when you call the RLock() function. If any other goroutine already called the WLock(), then it blocks. You can call any number of RLock() within the same goroutine, it won't lock.

### Concurrency and parallelism
Concurrency means the program can solve tasks simultaneously;
tasks are divided and switching between tasks is as fast as if they were running in parallel;
threads can be independent and can communicate with each other

Parallelism means the program can execute tasks, each task executes on the separate CPU

### channels
```go
// usual channel
ch := make(chan bool)
ch <- true // this operation is blocking the following code! // DEADLOCK
<- ch

// buffered channel
ch := make(chan bool, 1)
ch <- true // this operation is not blocking the next code; 
<- ch

// closing channels
// goroutins will be unlocked, receivers will get default values, senders will panic
close(ch)

// <-
// the second value is boolean, and it is false if channel was closed
val, isOpen := <- ch
```
#### channels under the hood
```
qcount - values count in the buffer
dataqsiz - size of the buffer
buf - pointer of the buffer
closed - is channel closed
recvq - pointer of the linked list of the goroutines waiting for read
sendq - pointer of the linked list of the goroutings waiting for write
lock - mutex for safety
```


### interfaces
```go
type iface struct {
    tab  *itab // pointer for struct that stores info about methods or other metadata
    data unsafe.Pointer // pointer for variable
}
```

**duck typing** - it means implicit implementation
```go
type Stringer interface{
	String() string
}

type SomeStruct struct{
	a string
}

// implicit implementation!
// because you are not declare definition as 
// type SomeStruct struct implements Stringer
// it's just a method
func (s SomeStruct) String() string {
	return s.a
}
```