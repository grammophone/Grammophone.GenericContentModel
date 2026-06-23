# ReadOnlySequence<T>

`ReadOnlySequence<T>` is a serializable read-only ordered collection.

It preserves item order, supports zero-based index access, exposes `Count`, and can return a cached array representation through `ToArray()`. Unlike `ReadOnlyBag<E>`, it preserves duplicates and positional identity.

Use `ReadOnlySequence<T>` when order matters and consumers should not mutate the sequence directly.
