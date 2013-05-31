# Protocal

>
That it doesn't matter who you are, or where you come from: anyone can achieve anything if they work hard enough.

In order for the table view to know whether an object is suitable as a data source, it’s important to be able to declare that the object implements the necessary methods.

## An example

```objc
@protocal Talking <NSObject>
- (Mouth)mouth;
- (void)say:(NSString *)word;
@optional
- (void)yell:(NSString *)word;
@end
```

Class use this protocal:

```objc
// Miao.h
@interface Miao : NSObject <Talking, Walking>
@property (Mouth)mouth;
@end
```

```objc
// Miao.m
@implement Miao
- (void)say:(NSString *)word {
  NSLog(@"Hi");
}
@end
```

Check whether an object implements that method:

```objc
if([miao respondsToSelector: @selector(yell:)]) {
  // Yell!
}
```

or

```objc
if([Miao instancesRespondToSelector: @selector(yell:)]) {
  // Yell twice!
}
```

## Inherit

It’s best practice to define your protocols
to conform to the NSObject protocol.

```objc
@protocol MyProtocol <NSObject>
  // ...
@end
```

## Used for Anonymity

```objc
id <XYZFrameworkUtility> utility = [frameworkObject anonymousUtility];
```

Even though you don’t know the class of a object, 
the protocol dictates that it can respond to the messages.

## Refs:

https://developer.apple.com/library/mac/#documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/WorkingwithProtocols/WorkingwithProtocols.html
http://nshipster.com/at-compiler-directives/

