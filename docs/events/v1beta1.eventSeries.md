
## eventSeries
EventSeries contain information on series of events, i.e. thing that was/is happening continuously for some time.

**Functions:**

[`fn .withCount`](#fn-withcount)  
[`fn .withLastObservedTime`](#fn-withlastobservedtime)  
[`fn .withState`](#fn-withstate)  

---


### `fn .withCount`
Number of occurrences in this series up to the last heartbeat time
```jsonnet
{
  withCount(count):: {}
}
```

### `fn .withLastObservedTime`
MicroTime is version of Time with microsecond level precision.
```jsonnet
{
  withLastObservedTime(lastObservedTime):: {}
}
```

### `fn .withState`
Information whether this series is ongoing or finished. Deprecated. Planned removal for 1.18
```jsonnet
{
  withState(state):: {}
}
```
