# flatten-interval-tree
Interval Tree implementation as it is described in Cormen et al. (2009, Section 14.3: Interval trees, pp. 348–354).

## Installation
npm install flatten-interval-tree -save

## Usage

    let IntervalTree = require('flatten-interval-tree');

## API Reference

## Constructor
Create new instance of interval tree

    let tree = new IntervalTree();

## Insert(key, value)
Insert new item into the tree. Key is and interval object or an array of [low, high] numeric values.
Value may represent any value or refer to an object. If value omitted, tree will store and retrieve keys only.
If key is an object, it should implement the following methods: less_than, equal_to, intersect,
clone, output, maximal_val, val_less_than.
Method returns reference to the inserted node

    let node = tree.insert(key, value);

## Exist(key,value)
Method returns true if entry {key, value} exists in the tree.
Method mey be useful if need to support unique items.

    let exist = tree.exist(key,value);

## Remove(key, value)
Removes item from the tree. Returns true if item was actually deleted, false if not found

    let removed = tree.remove(key, value);

## Search(interval)
Returns array of entry values which keys intersect with given interval
If tree stores only keys with no values, search returns array of keys which intersect given interval

    let resp = tree.search(interval);

## Size (getter)
Returns number of entries stored in the tree

    let size = tree.size;

## ForEach(visitor)
Enables to traverse the whole tree and perform operation for each item

    tree.forEach( (key, value) => console.log(value) )

## Tests

    npm test

## Contributors

In lieu of a formal style guide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code.

## License

MIT


