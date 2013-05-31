# Property

```objc
@interface UserModel : NSObject
@property (readwrite) NSString* name;
@end
```

Set age to be available with read and write access (getter and setter)

## Dot syntax

```objc
NSString *firstName = somePerson.firstName;
somePerson.firstName = @"Johnny";
```

Ruby:

```ruby
attr_accessor, attr_reader, attr_writer
```

## In Initializer

A typical intializer

```objc
- (id)init {
    self = [super init];

    if (self) {
        // initialize instance variables here
    }

    return self;
}
```

With custom initializer:

```objc
- (id)initWithFirstName:(NSString *)aFirstName lastName:(NSString *)aLastName {
    self = [super init];

    if (self) {
        // Use `_firstName`, not `self.firstName = aFirstName`
        _firstName = aFirstName;
        _lastName = aLastName;
    }

    return self;
}
```

### modifiers

#### readwrite, readonly

readwrite: getter and setter
readonly: getter

#### atomic (default), nonatomic

This means that the synthesized accessors ensure that a value is
always fully retrieved by the getter method or fully set
via the setter method, even if the accessors are called simultaneously
from different threads.

But Property atomicity is not synonymous with an object’s thread safety.

#### strong (default), weak, copy

In Objective-C, an object is kept alive as long as it has at least
one strong reference to it from another object.

##### Weak local variable use `__weak`

```objc
NSObject * __weak weakVariable;
```

##### copy

Create new object, Use a strong reference, because it must hold on
to the new object it creates.

Any object that you wish to set for a copy property must confirm
`NSCopying` protocal.

## Refs:

http://developer.apple.com/library/mac/#documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/EncapsulatingData/EncapsulatingData.html#//apple_ref/doc/uid/TP40011210-CH5-SW1

