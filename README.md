# BusterWood.Channels
[CSP-like](https://en.wikipedia.org/wiki/Communicating_sequential_processes) channels for .NET 4.6 or above.

The `Channel<T>` has the following methods:

* `T Receive()` reads a value from the channel, blocking until a sender has sent a value.
* `Task<T> ReceiveAsync()` reads a value from the channel, the returned task will only complete when a sender has written the value to the channel.
* `bool TryReceive(out T)` attempts to read a value from the channel, returns FALSE is no sender is ready.
* `void Send(T)` writes a value to the channel, blocking until a receiver has got the value.
* `Task SendAsync(T)` writes a value to the channel, the returned task will only complete when a receiver has got the value.
* `bool TrySend(T)` attempts to write a value to the channel, returns FALSE is no receiver is ready.
* `void Close()` prevents any further attempts to send to the channel
* `bool IsClosed` has the channel been closed?