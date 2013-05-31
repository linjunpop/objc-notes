# Block

## Basic

```objc
^{
    NSLog(@"This is a block");
}
```

Ruby:

```ruby
lambda {
  puts "This is a lambda"
}
```

Declare a block variable `simpleBlock` accept no argument and return `void`:

```objc
void (^simpleBlock)(void);
```

Ruby:

```ruby
foo = Proc.new {}
```

Assign a block to the variable:

```objc
simpleBlock = ^{
    NSLog(@"This is a block");
};
```

Ruby:

```ruby
foo = Proc.new {
  puts "This is a proc"
}
```

Combine declaration and assignment:

```objc
void (^simpleBlock)(NSString *s) = ^{
    NSLog(@"This is a block");
};
```

Ruby:

```ruby
foo = lambda { |a|
  puts "foobar - #{a}"
}
```

## Blocks Can Capture Values from the Enclosing Scope

```objc
- (void)testMethod {
    int anInteger = 42;
 
    void (^testBlock)(void) = ^{
        NSLog(@"Integer is: %i", anInteger);
    };
    
    anInteger = 84;
 
    testBlock();
}
// => Integer is: 42
```

Ruby:

```ruby
# TODO
```

## Use __block Variables to Share Storage

```objc
__block int anInteger = 42;

void (^testBlock)(void) = ^{
    NSLog(@"Integer is: %i", anInteger);
};

anInteger = 84;

testBlock();
// => Integer is: 84
```

Side effect:

Any Objective-C objects declared in this way will not be sent a -retain message. Another side-effect is that the variable will be shared by all blocks which access it, so modifications made by one block will be seen by another— they will not have their own mutable copies of the variable’s initial value.

Ruby:

```ruby
a = 42
foo = lambda {
  puts "Integer is #{a}"
}
a = 64
foo.call()

#=> Integer is: 64
```

## Refs:

http://developer.apple.com/library/ios/#documentation/cocoa/conceptual/ProgrammingWithObjectiveC/WorkingwithBlocks/WorkingwithBlocks.html

