# Grammophone.GenericContentModel
This .NET Standard 2.0 library offers various collection extensions. These include automatic indexing by a key field of their elements, automatic "composite pattern", i.e. elements automatically aware of their "owner" who exclusively holds their collection, multivalued dictionaries, observable sets, in read-only and read-write variants.

Element types that are indexed by a key field of type `K` must implicitly or explicitly implement `IKeyedElement<K>`. Element types that are aware of their owner of type `P` must implement `IChild<P>`. Element types that support both of the above should implement `IKeyedChild<K, P>`. The UML diagram of these interfaces follows:

![Keyed and owned elements interfaces](https://raw.githubusercontent.com/grammophone/Grammophone.GenericContentModel/master/Images/GenericContentModel%20elements.png)

The collection interfaces offered are shown on the next UML diagram. All interfaces have serializable concrete implementations with corresponding name. In the interface and class names, the 'Bag' is a simple collection with `Count` discoverable in O(1), 'Children' is an owner-aware collection having elements which are also owner-aware, 'Sequence' or 'Ordered' is an ordered collection, 'Map' or 'Keyed' is a indexing collection aware of element keys.

![Interface hierarchy of content models](https://raw.githubusercontent.com/grammophone/Grammophone.GenericContentModel/master/Images/GenericContentModel%20interfaces.png)

### `ObservableHashSet<T>`

`ObservableHashSet<T>` is a `HashSet<T>`-based collection that implements `INotifyCollectionChanged` and `INotifyPropertyChanged`.

It is intended for models that need set semantics together with notification-based observers. One common use is entity collection navigation properties where notification-based change tracking is required, without referencing ORM-specific collection types from the domain model.

Read more in the detailed [documentation](documentation/observable-hash-set.md).

This library has no dependencies.

