## Java distributed Unique ID generator inspired by Twitter snowflake

You can read about Twitter snowflake [here](https://blog.twitter.com/engineering/en_us/a/2010/announcing-snowflake.html).

The IDs are 64-bits in size and are generated with the combination of the following:

+ **Epoch timestamp in milliseconds precision** - **42 bits**. The maximum timestamp that can be represented using 42 bits is 242 - 1, or 4398046511103, which comes out to be Wednesday, May 15, 2109 7:35:11.103 AM. That gives us 139 years with respect to a custom epoch.
+ **Node ID** - **10 bits**. This gives us 1024 nodes/machines.
+ **Local counter per machine** - **12 bits**. The counter’s max value would be 4095.

## How to use

The `SequenceGenerator` class should be used as a singleton in your application.

```java
SequenceGenerator s = new SequenceGenerator()
s.nextId()
```

Read the blog to understand more:

- [Generating unique IDs in a distributed environment at high scale.](https://www.callicoder.com/distributed-unique-id-sequence-number-generator/)
