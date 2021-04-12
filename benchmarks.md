# benchmarks

### Memory
```shell script
go tool pprof -alloc_space converttest.test mem.out

go tool pprof -alloc_space cryptoswitch.test mem.out

top

list BenchmarkCryptoSwitch_Encrypt_CBC

```

