# Protocal

```objc
@protocal Talking

- (void)say:(NSString *)word;

@end

// Miao.h
@interface Miao<Talking>
@end

// Miao.m
@implement Miao
- (void)say:(NSString *)word {
  NSLog(@"Hi");
}
@end
```

