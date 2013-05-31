# Categories

"A category allows you to add methods to an existing class—even to one for which you do not have the source."

```objc
#import <Foundation/Foundation.h>
 
@interface AClass (ACategory)
 
@end
```

File: `NSDate+Formatting.h`

```objc
#import <Foundation/Foundation.h>
 
@interface NSDate (Formatting)
 
- (NSString*) timeAgoInWords;
 
@end

```

File: 'NSDate+Formatting.m'

```objc
#import "NSDate+Formatting.h"
 
@implementation NSDate (Formatting)
 
- (NSString *)timeAgoInWords {
    // ...
}

@end

```

Usage:

```objc
NSDate* oldDate = [NSDate dateWithTimeIntervalSinceNow:180];
NSLog(@"Date was %@", oldDate.timeAgoInWords); // => 3 minutes ago
```

Ruby:

```ruby
class String
  def blank?
    true
  end
end

"foo".blank? #=> true
```

Refs:

http://blog.carbonfive.com/2012/01/23/monkey-patching-ios-with-objective-c-categories-part-1-simple-extensions-and-overrides/

