# Objective-C KVO Bug: Missing willChangeValueForKey and didChangeValueForKey

This repository demonstrates a common error encountered when using Key-Value Observing (KVO) in Objective-C.  If a custom class's setter method for an observed property fails to call `willChangeValueForKey:` and `didChangeValueForKey:`, KVO will not function as expected. This can result in unexpected behavior, where observers are not notified of changes to the observed property.

The `BuggyKVOClass.m` file contains the buggy code, while `FixedKVOClass.m` shows the corrected implementation.

## Reproducing the Bug

1. Clone this repository.
2. Open the project in Xcode.
3. Run the application.
4. Observe that the KVO observer in `BuggyKVOClass` does not receive the update.  
5. Now run the application with `FixedKVOClass` to see the corrected behavior.