# MongoDB $inc operator with string value
This code demonstrates an uncommon error that can occur when using the `$inc` operator in MongoDB update operations.

The `$inc` operator is used to increment a numerical field by a specified value.  However, if you provide a string value instead of a number, the operation will fail silently.  This can be difficult to debug, as there is no obvious error message.

This example shows the incorrect usage and provides the correct solution.

## Bug
The bug lies in using a string ('abc') instead of a number (e.g., 1) as the increment value with the `$inc` operator. This will not throw an error but it won't update the document correctly either.  MongoDB will essentially ignore this incorrect operation.

## Solution
Ensure that the value provided to the `$inc` operator is a valid number.