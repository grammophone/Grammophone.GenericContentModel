# Children<P, C>

`Children<P, C>` is the mutable counterpart of `ReadOnlyChildren<P, C>`.

Adding a child assigns its `Parent` to the collection owner. Removing a child clears its `Parent`. Clearing the collection clears the parent of every contained child.

Use it for mutable composite-pattern collections where the collection owns the child-parent relationship.
