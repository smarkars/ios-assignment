# iOS Engineer Challenge

## Calendar and Agenda Views

Build an iOS app that replicates the basic features described below of the Calendar view from the [Sunrise iOS (iPhone) app](https://itunes.apple.com/us/app/sunrise-calendar./id599114150?mt=8).

We've highlighted the primary features of the views below. You can decide which other details to implement and any new features you can come up with.

### Calendar View

![](http://cl.ly/image/032R1A0K181e/content)

The calendar view is a freely scrolling view that allows the user to browse between days of the year. Tapping on a date should display number of meetings in a Alert.



## Instructions

Create a new private GitHub repository and push your commits to it as you are completing the challenge.

Once you are ready, add someone from the Sunrise team to the repository and send an email for us to review it.

Don't hesitate to ask us questions. Displaying creativity is a bonus in all challenges.

## What We Look For

### Code Consistency

The code should be consistently formatted. Consistent code reduces syntax related distractions and helps us focus on the important logic. Use a code linter if necessary to help you spot these inconsistencies.

*Example of Inconsistent Code:*

```java
if (a == b) {
  //
} else if (a == c)
{
  //
}
else {
  //
}
```

### Variable Naming Clarity

We should be able to understand the logic of code blocks by reading the names of variables and functions. A clearly named variable means we won't need to look up the definition of the variable or function right away in order to understand what it does.

*Example of Clear Code:*

```js
var listEvents = function(cb) {
  var tasks = [
    fetchEventsForSharedCalendars,
    fetchEventsForUserCalendars
  ];
  parallel(tasks, function(error, results) {
    if (error) {
      log.error(error);
      return cb(error);
    }

    var events = flatten(results);
    return cb(null, events);
  });
};
```

### Useful Comments

A comment should be used in cases where the code cannot be formatted to fix clarity. The comment should allow us to skip over code blocks when looking for an overview of the code. We can come back later to the smaller bits of code to confirm they do what the comment says.

*Example of Useful Comments:*

```objc
for (NSNumber *timestamp in timestampArray) {
  // Create Start Date
  NSDate *startDate = [NSDate dateWithTimeIntervalSince1970:icaltime_as_timet([timestamp doubleValue])];

  // Ignore Before Earliest Date
  if ([startDate compare:earliestDate] == NSOrderedAscending) {
      continue;
  }

  // Ignore EXDATE
  BOOL isExcludedDate = NO;
  for (NSDate *excludedDate in excludedDates) {
      if ([startDate isEqualToDate:excludedDate]) {
          isExcludedDate = YES;
      }
  }
  if (isExcludedDate == YES) {
      continue;
  }

  // Ignore After Latest Date
  if ([startDate compare:latestDate] == NSOrderedDescending) {
      continue;
  }

  // Save Valid Start Date
  [datesArray addObject:startDate];
}
```

### Unit Tests

Write unit tests for critical parts of your app. The process of writing tests for your code also reminds you of input cases that you may have missed before.

*Example of Multiple Input Unit Tests:*

```objc
- (void)testEncodedURLQueryString
{
    NSDictionary *dictionary = nil;

    // Should return nil on non-NSString values
    dictionary = @{@"key": [[UIView alloc] init]};
    XCTAssert([dictionary queryString] == nil);

    // Should return nil on nested values
    dictionary = @{@"key": @{@"key1": @"value1"}};
    XCTAssert([dictionary queryString] == nil);

    // Should return urlEncoded key value pairs joined with `&`
    dictionary = @{@"key#0": @"value#0", @"key#1": @"value#1"};
    XCTAssert([[dictionary queryString] isEqualToString:@"key%230=value%230&key%231=value%231"]);
}
```
