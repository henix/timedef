# timedef

Time constants for better code readability

## Example

```ts
10 * SECOND // 10 seconds in milliseconds
15 * MINUTE // 15 minutes in milliseconds
```

```ts
cache.set("key", "value", { ttl: 600 }); // bad, 600 is a magic number

cache.set("key", "value", { ttl: 10 * MINUTE / SECOND }); // good, 600 is 10 minutes in seconds
```

## Related projects

This package is inspired by Scala's [Duration API](https://www.scala-lang.org/api/2.13.1/scala/concurrent/duration/Duration.html):

```scala
duration < 1.second
```

In C++ 14, we can do [postfix op magic](https://en.cppreference.com/w/cpp/chrono/operator%22%22min) with the standard library:

```cpp
auto lesson = 45min
```

Java's standard library is deeply integrated with the [TimeUnit](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/TimeUnit.html) class. You usually should pass a number with a `TimeUnit` when a method needs a duration:

* [Future.get](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/Future.html#get-long-java.util.concurrent.TimeUnit-)
* [ScheduledExecutorService.schedule](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ScheduledExecutorService.html#schedule-java.lang.Runnable-long-java.util.concurrent.TimeUnit-)

## License

MIT
