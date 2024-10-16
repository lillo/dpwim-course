# Exercises on Go Programming (part 2)

## Exercise 1
Write a function `isFunction` that takes a relation `r` on integers as input, i.e., a list of pair `(x,y)` of integers, and returns `true` if `r` represents a valid function. For example, `isFunction` `r1` where `r1 = [(1,1); (2,2); (3,3)]` returns true because `r1` represents the identity function on the set `{1,2,3}`. Instead, `isFunction` `r2` with `r2 = [(1,2); (2,4); (3,6); (4,8); (1,0)]` returns false because `r2` cannot be a function.

## Exercise 2
Write a function `count_change` that given a list of coin denominations `d` and an amount of money `n`, returns in how many ways we can make the change.

For example, given `d = [1; 3; 5; 7]` and `n = 8` the result of `count_change d n` is `6`, because the possible changes are
```
[1;7]
[3;5]
[1;1;3;3]
[1;1;1;5]
[1;1;1;1;1;3]
[1;1;1;1;1;1;1;1]
```

Given `d = [1;2;3]` and `n = 4` the result of `count_change d n` is `4`, because the possible changes are
```
[1;3]
[2;2]
[1;1;2]
[1;1;1;1]
```

## Exercise 3
A [leftist heap](https://en.wikipedia.org/wiki/Leftist_tree) is a variant of a binary heap, where every node `x` has an *s-value* which is the distance to the nearest leaf in subtree rooted at `x`.
In contrast to a binary heap, a leftist tree can be  unbalanced. In addition to the heap property, leftist trees are maintained so the right descendant of each node has the lower s-value.

Implement a leftist heap by completing the following draft implementation 
```go
type Heap interface {
	Insert(int) Heap
	Merge(Heap) Heap
	GetMax() (int, error)
	DeleteMax() (Heap, error)
	GetRank() (int, error)
}

type leaf struct{}

type node struct {
	data  int
	left  Heap
	right Heap
	rank  int
}

func Empty() Heap {
	//...
}

func Singleton(n int) Heap {
	//...
}
```