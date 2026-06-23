# RelationshipBuilder

`RelationshipBuilder` provides helpers for applying many-to-many relationship definitions.

The `ActManyToMany` methods accept relationship tuples and invoke one action per object on each side, passing the associated objects from the opposite side. Overloads can also receive the full set of objects on both sides so objects without tuples are still processed with empty association collections.

Use it when a tuple-based relationship definition must populate or synchronize both ends of an object relationship.
