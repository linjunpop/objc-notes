# Property

```objc
// Interface
#import <Foundation/Foundation.h>

@interface UserModel : NSObject

@property (retain) NSString* name;

@end

// Implementation
#import "UserModel.h"

@implementation UserModel

@synthesize name;

@end
```

Set age to be available with read and write access (getter and setter)
we want the argument to be assigned to the property.

Ruby:

```ruby
attr_accessor, attr_reader, attr_writer
```
