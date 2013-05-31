# Message

```objc
[you say:@"Hello."];
```

Ruby:

```ruby
you.say('Hello')
```

In particular, Objective-C’s:

```objc
[apple performSelector:@selector(eat:)
                        withObject:camembert]; // Equivalent to [apple eat:camembert];
```

Would be equivalent to Ruby’s:

```ruby
apple.send(:eat, camembert)
```

Sadly, we CANNOT use

```objc
[apple performSelector:@selector(@"eat:")
                        withObject:camembert];
```

Another way:

```objc
id objc_msgSend(id theReceiver, SEL theSelector, ...)
```

