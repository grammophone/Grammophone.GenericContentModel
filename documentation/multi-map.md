# MultiMap<K, E>

`MultiMap<K, E>` is the mutable counterpart of `ReadOnlyMultiMap<K, E>`.

Elements must implement `IKeyedElement<K>`. Adding an item groups it under its key, and removing an item also removes the key bucket when it becomes empty.

Use `MultiMap<K, E>` for mutable one-to-many keyed collections where each element supplies its own key.
