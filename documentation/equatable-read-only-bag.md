# EquatableReadOnlyBag<T>

`EquatableReadOnlyBag<T>` extends `ReadOnlyBag<T>` with set equality and hash-code support.

The element type must implement `IEquatable<T>`. Equality is based on set membership, not enumeration order. The class caches a calculated hash code and recalculates it after deserialization.

Use it when a read-only set-like collection must itself be compared, stored in a set, or used as a dictionary key.
