# KeyedChild<P, K>

`KeyedChild<P, K>` is an abstract base implementation of `IKeyedChild<P, K>`.

It combines the `Parent` property inherited from `Child<P>` with a protected-set `Key` property supplied at construction time.

Use it for composite-pattern child objects that must also be addressable by key.
