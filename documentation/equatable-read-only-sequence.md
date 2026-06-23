# EquatableReadOnlySequence<T>

`EquatableReadOnlySequence<T>` extends `ReadOnlySequence<T>` with item-by-item equality and hash-code support.

The element type must implement `IEquatable<T>`. Equality requires the same item count and equal items in the same positions. The class caches a calculated hash code and recalculates it after deserialization.

Use it when an ordered sequence value must participate in equality comparisons, dictionary keys, or set membership.
