## count() is implemented as return (find(__k) != end());

## The choice depends on the semantics in your code. If you want just to check if a key exist, you could just use `count`. If you would like to check if a key exists, and use its value, then go for `find` since you will already have an iterator pointing to that element.
