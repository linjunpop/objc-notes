# Extensions

Extensions look like categories, but omit the category name. These are typically declared before an @implementation to specify a private interface, and even override properties declared in the interface:

```objc
@interface MyObject ()
@property (readwrite, nonatomic, strong) NSString *name;
- (void)doSomething;
@end

@implementation MyObject
@synthesize name = _name;

// ...

@end
```
