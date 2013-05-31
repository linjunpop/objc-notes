# Interface

Header file: `UserModel.h`

```objc
#import <Foundation/Foundation.h>

@interface UserModel : NSObject

+ (NSMutableArray *)all;

@end
```

Implementation file: `UserModel.m`

```objc
#import "UserModel.h"

@implementation UserModel

+ (NSMutableArray *)all {
    // ...
}

@end
```
