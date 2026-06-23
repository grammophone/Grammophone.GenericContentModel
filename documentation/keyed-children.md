# KeyedChildren<P, K, C>

`KeyedChildren<P, K, C>` is the mutable counterpart of `KeyedReadOnlyChildren<P, K, C>`.

Adding a child indexes it by key and assigns its parent. Removing by key or by item clears the child's parent when the item is removed.

Use it for mutable keyed child collections that must keep parent references synchronized.
