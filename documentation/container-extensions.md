# ContainerExtensions

`ContainerExtensions` provides extension methods for building multi-dictionaries from ordinary sequences.

The `ToMultiDictionary` overloads group source items by a key mapper. Values can either be the source items themselves or values produced by a value mapper. Generic overloads also allow the collection type stored under each key to be customized.

Use these helpers when LINQ-style grouping should produce this library's `MultiDictionary` abstractions instead of standard lookup types.
