## 1.0.0

- the first version

## 1.1.0

- FRefreshController added control function   
    `scrollTo(double position, {Duration duration = const Duration(milliseconds: 300)})`
    `scrollBy(double position, {Duration duration = const Duration(milliseconds: 300)})`
    `jumpTo(double postion)`
    
- FRefreshController adds `double position`,` ScrollMetrics scrollMetrics` and other parameters to get sliding information

- FRefreshController adds a useful parameter `backOriginOnLoadFinish`. When loading is completed, whether to return to the original position. For example, when the GridView adds only one element, this parameter is useful.

## 1.1.1

- `onRefresh` and `onLoad` can return any value to stop refreshing automatically, without going through FRefreshController. E.g:

```dart
FRefresh(
  ...,

  onRefresh: () async {
    await Future(duration: Duration(milliseconds: 3000));

    /// Actively stop refreshing
    returen true;
  },

  onLoad: () async {
    await Future(duration: Duration(milliseconds: 3000));
  
    /// Actively stop loading
    returen true;
  }
)
```
