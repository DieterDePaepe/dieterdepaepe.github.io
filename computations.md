# Sliding window

## Sliding window minimum

Runtime: O(n)  
Memory: O(k)

```python
from collections import namedtuple
from collections import deque

Entry = namedtuple("Entry", ["value", "expire"])

def min_window(data, window):
    queue = deque()
    
    for i, value in enumerate(data):
        while queue and queue[-1].value >= value:
            queue.pop()
        queue.append(Entry(value, i + window))
        if queue[0].expire == i:
            queue.popleft()
        
        yield(queue[0].value)
        
data =    [0, 1, 2, 3, 4, 5, 3, 1, 2, 2, 2, 6, 2, 0, 4, 5, 4, 3, 2, 1, 0]
correct = [0, 0, 0, 1, 2, 3, 3, 1, 1, 1, 2, 2, 2, 0, 0, 0, 4, 3, 2, 1, 0]

assert(correct == list(min_window(data, 3)))
```

## Sliding window standard deviation

http://matlabtricks.com/post-20/calculate-standard-deviation-case-of-sliding-window

# Statistics

## Variance

https://en.wikipedia.org/wiki/Algorithms_for_calculating_variance

http://matlabtricks.com/post-19/calculating-standard-deviation-using-minimal-memory



# Precision

## Summation of floats

https://en.wikipedia.org/wiki/Kahan_summation_algorithm

