# ObservableHashSet

`ObservableHashSet<T>` is a `HashSet<T>`-based collection that implements `INotifyCollectionChanged` and `INotifyPropertyChanged`.

It is intended for models that need set semantics together with notification-based observers. One common use is entity collection navigation properties where notification-based change tracking is required, without referencing ORM-specific collection types from the domain model.

## Why It Exists

The built-in `ObservableCollection<T>` provides change notifications, but it has list semantics:

- duplicates are allowed
- membership checks are linear
- removal by value is linear

Many models prefer set semantics for relationship collections. `ObservableHashSet<T>` keeps set behavior while providing change notifications.

## Example

```csharp
public class Artist
{
	public virtual int ID { get; set; }

	public virtual string Name { get; set; }

	public virtual ICollection<Album> Albums { get; set; }
		= new ObservableHashSet<Album>();
}
```

This keeps the public property typed as `ICollection<Album>` while using a notification-capable set implementation.

## Behavior

`ObservableHashSet<T>` raises `CollectionChanged` for actual additions and removals. It also raises `PropertyChanged` for `Count` whenever the collection changes.

The implementation forwards mutating `ICollection<T>` and `ISet<T>` interface calls to the notifying methods, so common navigation-property usage such as this raises notifications:

```csharp
artist.Albums.Add(album);
artist.Albums.Remove(album);
```

Bulk set operations such as `UnionWith`, `ExceptWith`, `IntersectWith`, `SymmetricExceptWith` and `RemoveWhere` report the actual items that were added or removed.

## Equality Comparers

Custom equality comparers are supported through the standard `HashSet<T>` constructors:

```csharp
var set = new ObservableHashSet<string>(StringComparer.OrdinalIgnoreCase);
```

Bulk operations use the set's comparer when determining which items are actually added or removed.

## Limitations

`ObservableHashSet<T>` inherits from `HashSet<T>`. `HashSet<T>` methods are not virtual, so notifications can be bypassed if the instance is explicitly cast to `HashSet<T>` and mutated through the base type.

Use it through `ObservableHashSet<T>`, `ICollection<T>` or `ISet<T>` references for notification-aware mutations.

The collection is not thread-safe, matching the behavior of `HashSet<T>`.
