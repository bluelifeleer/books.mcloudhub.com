#### for

##### 循环使用

```
let interestingNumbers = [
    "Prime": [2, 3, 5, 7, 11, 13],
    "Fibonacci": [1, 1, 2, 3, 5, 8],
    "Square": [1, 4, 9, 16, 25],
]
var largest = 0
for (kind, numbers) in interestingNumbers {
    for number in numbers {
        if number > largest {
            largest = number
        }
    }
}
print(largest)
```

> 在循环中可以使用..<指定一个索引。

```
var total = 0
for i in 0..<4 {
    total += i
}
print(total)
```

#### while