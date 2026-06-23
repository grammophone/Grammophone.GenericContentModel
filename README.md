# Grammophone.GenericContentModel
This .NET Standard 2.0 library offers various collection extensions. These include automatic indexing by a key field of their elements, automatic "composite pattern", i.e. elements automatically aware of their "owner" who exclusively holds their collection, multivalued dictionaries, observable sets, in read-only and read-write variants.

Element types that are indexed by a key field of type `K` must implicitly or explicitly implement `IKeyedElement<K>`. Element types that are aware of their owner of type `P` must implement `IChild<P>`. Element types that support both of the above should implement `IKeyedChild<K, P>`. The UML diagram of these interfaces follows:

![Keyed and owned elements interfaces](https://raw.githubusercontent.com/grammophone/Grammophone.GenericContentModel/master/Images/GenericContentModel%20elements.png)

The collection interfaces offered are shown on the next UML diagram. All interfaces have serializable concrete implementations with corresponding name. In the interface and class names, the 'Bag' is a simple collection with `Count` discoverable in O(1), 'Children' is an owner-aware collection having elements which are also owner-aware, 'Sequence' or 'Ordered' is an ordered collection, 'Map' or 'Keyed' is a indexing collection aware of element keys.

![Interface hierarchy of content models](https://raw.githubusercontent.com/grammophone/Grammophone.GenericContentModel/master/Images/GenericContentModel%20interfaces.png)

## Classes

### `ReadOnlyBag<E>`

`ReadOnlyBag<E>` is a serializable read-only set-backed collection with O(1) `Count` and duplicate suppression.

Read more in the detailed [documentation](documentation/read-only-bag.md).

### `ReadOnlySequence<T>`

`ReadOnlySequence<T>` is a serializable read-only ordered collection with index access and cached array conversion.

Read more in the detailed [documentation](documentation/read-only-sequence.md).

### `EquatableReadOnlyBag<T>`

`EquatableReadOnlyBag<T>` is a read-only bag that supports set equality and stable hash codes for equatable elements.

Read more in the detailed [documentation](documentation/equatable-read-only-bag.md).

### `EquatableReadOnlySequence<T>`

`EquatableReadOnlySequence<T>` is a read-only sequence that supports item-by-item equality and hash-based lookup scenarios.

Read more in the detailed [documentation](documentation/equatable-read-only-sequence.md).

### `ReadOnlyMap<K, E>`

`ReadOnlyMap<K, E>` is a read-only collection of keyed elements indexed by each element's `Key` property.

Read more in the detailed [documentation](documentation/read-only-map.md).

### `Map<K, E>`

`Map<K, E>` is the mutable counterpart of `ReadOnlyMap<K, E>` for keyed element collections.

Read more in the detailed [documentation](documentation/map.md).

### `ReadOnlyMultiMap<K, E>`

`ReadOnlyMultiMap<K, E>` is a read-only keyed collection that allows multiple elements to share the same key.

Read more in the detailed [documentation](documentation/read-only-multi-map.md).

### `MultiMap<K, E>`

`MultiMap<K, E>` is the mutable counterpart of `ReadOnlyMultiMap<K, E>`.

Read more in the detailed [documentation](documentation/multi-map.md).

### `ReadOnlyMultiDictionary<K, E, C, CI>`

`ReadOnlyMultiDictionary<K, E, C, CI>` and its shorthand variants are read-only dictionaries where each key maps to a collection of values.

Read more in the detailed [documentation](documentation/read-only-multi-dictionary.md).

### `MultiDictionary<K, E, C, CI>`

`MultiDictionary<K, E, C, CI>` and its shorthand variant are mutable dictionaries where each key maps to multiple values.

Read more in the detailed [documentation](documentation/multi-dictionary.md).

### `ReadOnlyBiGramSet<F, S>`

`ReadOnlyBiGramSet<F, S>` and `ReadOnlyBiGramSet<T>` are read-only tuple sets indexed by both tuple members.

Read more in the detailed [documentation](documentation/read-only-bi-gram-set.md).

### `ReadOnlyKeyValuePair<K, V>`

`ReadOnlyKeyValuePair<K, V>` is a serializable immutable key-value pair implementing `IReadOnlyKeyValuePair<K, V>`.

Read more in the detailed [documentation](documentation/read-only-key-value-pair.md).

### `Child<P>`

`Child<P>` is a base implementation for objects that keep a reference to their parent.

Read more in the detailed [documentation](documentation/child.md).

### `KeyedChild<P, K>`

`KeyedChild<P, K>` is a base implementation for child objects that also expose a key.

Read more in the detailed [documentation](documentation/keyed-child.md).

### `ReadOnlyChildren<P, C>`

`ReadOnlyChildren<P, C>` is a read-only child collection that assigns an owner to every contained child.

Read more in the detailed [documentation](documentation/read-only-children.md).

### `Children<P, C>`

`Children<P, C>` is the mutable counterpart of `ReadOnlyChildren<P, C>`.

Read more in the detailed [documentation](documentation/children.md).

### `KeyedReadOnlyChildren<P, K, C>`

`KeyedReadOnlyChildren<P, K, C>` is a read-only child collection indexed by child key.

Read more in the detailed [documentation](documentation/keyed-read-only-children.md).

### `KeyedChildren<P, K, C>`

`KeyedChildren<P, K, C>` is the mutable counterpart of `KeyedReadOnlyChildren<P, K, C>`.

Read more in the detailed [documentation](documentation/keyed-children.md).

### `OrderedKeyedReadOnlyChildren<P, K, C>`

`OrderedKeyedReadOnlyChildren<P, K, C>` is a read-only child collection indexed both by child key and by insertion position.

Read more in the detailed [documentation](documentation/ordered-keyed-read-only-children.md).

### `ObservableHashSet<T>`

`ObservableHashSet<T>` is a `HashSet<T>`-based collection that implements `INotifyCollectionChanged` and `INotifyPropertyChanged`.

It is intended for models that need set semantics together with notification-based observers. One common use is entity collection navigation properties where notification-based change tracking is required, without referencing ORM-specific collection types from the domain model.

Read more in the detailed [documentation](documentation/observable-hash-set.md).

### `ContainerExtensions`

`ContainerExtensions` provides LINQ-style helpers for building multi-dictionaries from sequences.

Read more in the detailed [documentation](documentation/container-extensions.md).

### `RelationshipBuilder`

`RelationshipBuilder` provides helpers for applying many-to-many relationship definitions to both relationship sides.

Read more in the detailed [documentation](documentation/relationship-builder.md).

This library has no dependencies.

