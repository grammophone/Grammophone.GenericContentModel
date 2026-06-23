# OrderedKeyedReadOnlyChildren<P, K, C>

`OrderedKeyedReadOnlyChildren<P, K, C>` is a read-only child collection indexed both by child key and by insertion position.

It extends `KeyedReadOnlyChildren<P, K, C>` with ordered enumeration, zero-based index access, and cached array conversion.

Use it when child objects need stable ordering and fast keyed lookup at the same time.
