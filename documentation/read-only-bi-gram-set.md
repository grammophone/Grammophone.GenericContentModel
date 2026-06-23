# ReadOnlyBiGramSet<F, S>

`ReadOnlyBiGramSet<F, S>` is a read-only set of `Tuple<F, S>` values indexed by both tuple members.

It supports lookups by first member, by second member, and by the full pair. `ReadOnlyBiGramSet<T>` is a shorthand for pairs whose first and second members have the same type.

Use it for immutable relationship pairs, especially when both sides of the pair need efficient reverse lookup.
