# ReadOnlyBag<E>

`ReadOnlyBag<E>` is a serializable read-only implementation of `IReadOnlyBag<E>` backed by a set.

It stores unique elements and exposes O(1) `Count`. The public surface is read-only, while initialization is supported internally through `IInitializable<E>` and protected add/remove hooks used by derived collection types.

Use `ReadOnlyBag<E>` when callers should enumerate and count a unique collection without being able to mutate it through the public API.
