<https://github.com/googleapis/google-cloud-go/wiki/Fine-Tuning-PubSub-Receive-Performance#subscriptionreceivesettingsmaxoutstandingmessages>


```go
// DefaultReceiveSettings holds the default values for ReceiveSettings.
var DefaultReceiveSettings = ReceiveSettings{
	MaxExtension:           60 * time.Minute, // период после которого сообщение уходит в повторную отправку
	MaxExtensionPeriod:     0, // период, после которого сообщение снова отправляется
	MinExtensionPeriod:     0,
	MaxOutstandingMessages: 1000, // кол-во сообщений которые можно читать без блокировки
	MaxOutstandingBytes:    1e9, // 1G размер сообщений которые можно читать без блокировки
	NumGoroutines:          10, 
}
```
