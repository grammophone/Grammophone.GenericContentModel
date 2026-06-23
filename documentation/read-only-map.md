# ReadOnlyMap<K, E>

`ReadOnlyMap<K, E>` is a serializable read-only implementation of `IReadOnlyMap<K, E>`.

Elements must implement `IKeyedElement<K>`. Each element is indexed by its `Key` property, giving dictionary-style lookup while still exposing the collection as a read-only set of elements.

Use `ReadOnlyMap<K, E>` when elements carry their own keys and consumers need fast lookup without public mutation.
