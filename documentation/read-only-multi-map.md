# ReadOnlyMultiMap<K, E>

`ReadOnlyMultiMap<K, E>` is a serializable read-only keyed collection where multiple elements can share the same key.

Elements must implement `IKeyedElement<K>`. Lookup by key returns a read-only bag of all matching elements. The class maintains the total element count separately from the number of keys.

Use it when elements carry their own keys, but the key relationship is one-to-many rather than one-to-one.
