As we've mentioned, Go does _not_ support classes. For a long time, that meant that Go code couldn't easily be reused in many cases. For example, imagine some code that splits a slice into 2 equal parts. The code that splits the slice doesn't care about the _types of values_ stored in the slice. Before generics, we needed to write the same code for each type, which is a very un-[DRY](https://blog.boot.dev/clean-code/dry-code/) thing to do.

```go
func splitIntSlice(s []int) ([]int, []int) {
    mid := len(s)/2
    return s[:mid], s[mid:]
}
```

```go
func splitStringSlice(s []string) ([]string, []string) {
    mid := len(s)/2
    return s[:mid], s[mid:]
}
```

In Go 1.18 however, support for [generics](https://blog.boot.dev/golang/how-to-use-golangs-generics/) was released, effectively solving this problem!

## Type Parameters

Put simply, generics allow us to use variables to refer to specific types. This is an amazing feature because it allows us to write abstract functions that drastically reduce code duplication.

```go
func splitAnySlice[T any](s []T) ([]T, []T) {
    mid := len(s)/2
    return s[:mid], s[mid:]
}
```

In the example above, `T` is the name of the type parameter for the `splitAnySlice` function, and we've said that it must match the `any` constraint, which means it can be anything. This makes sense because the body of the function _doesn't care_ about the types of things stored in the slice.

```go
firstInts, secondInts := splitAnySlice([]int{0, 1, 2, 3})
fmt.Println(firstInts, secondInts)
```