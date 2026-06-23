# KeyedReadOnlyChildren<P, K, C>

`KeyedReadOnlyChildren<P, K, C>` is a read-only parent-owned child collection indexed by child key.

Child items must implement `IKeyedChild<P, K>`. The collection assigns the owner as each child's parent and supports keyed lookup through the underlying map behavior.

Use it for immutable composite-pattern child collections where each child has a unique key.
