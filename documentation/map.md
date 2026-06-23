# Map<K, E>

`Map<K, E>` is the mutable counterpart of `ReadOnlyMap<K, E>`.

Elements must implement `IKeyedElement<K>`. Adding an element indexes it by its `Key`; removing can be done either by element or by key. Duplicate keys are not added.

Use `Map<K, E>` when you need a mutable keyed collection whose elements define their own keys.
