# ReadOnlyChildren<P, C>

`ReadOnlyChildren<P, C>` is a read-only collection of child objects belonging to a parent.

Child items must implement `IChild<P>`. When the collection owner is set, contained children have their `Parent` property set to that owner.

Use it for immutable composite-pattern collections where parent-child references must be kept in sync.
