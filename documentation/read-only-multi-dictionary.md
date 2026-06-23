# ReadOnlyMultiDictionary<K, E, C, CI>

`ReadOnlyMultiDictionary<K, E, C, CI>` is a read-only dictionary where each key maps to a collection of values.

The generic `C` parameter controls the public collection type returned for each key, and `CI` controls the concrete collection implementation. Shorthand variants are available when the value collection is a `ReadOnlyBag<E>` or when only the implementation type needs to vary.

The class can be created from key-value pairs, key-collection pairs, item collections with a key mapper, or master-detail collections.

Use it when values do not carry their own key, or when the grouping key is produced by a mapper rather than by `IKeyedElement<K>`.
