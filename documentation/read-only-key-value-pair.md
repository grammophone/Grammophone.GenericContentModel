# ReadOnlyKeyValuePair<K, V>

`ReadOnlyKeyValuePair<K, V>` is a serializable immutable key-value pair implementing `IReadOnlyKeyValuePair<K, V>`.

Both key and value are supplied at construction time and exposed through read-only properties. Equality compares both the key and value.

Use it when APIs need a lightweight immutable key-value object compatible with this library's read-only dictionary abstractions.
