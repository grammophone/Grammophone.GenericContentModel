# MultiDictionary<K, E, C, CI>

`MultiDictionary<K, E, C, CI>` is the mutable counterpart of `ReadOnlyMultiDictionary<K, E, C, CI>`.

Each key maps to a collection of values. The `C` and `CI` generic parameters allow the collection type under each key to be customized. The shorthand `MultiDictionary<K, E>` uses `ReadOnlyBag<E>` for each key's values.

Use it when keys should map to multiple values and the grouping key is supplied explicitly or by a mapper.
