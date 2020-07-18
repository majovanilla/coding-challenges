# Find the minimum number in a sorted and rotated array in less than O(n)

array = [4,5,6,7,8,3]
array2 = [9, 1, 2, 3, 4, 5, 6]

```
def find_min(array, start = 0, last = array.length)
  # find the middle
  middle = ((last - start)/2).floor
  # compare middle (3) to start (4) and end(3)
    if array[middle] > array[start] && array[middle] > array[last]
    # middle is larger than both
      #check the prev element of middle and the next element
      return array[middle] if array[middle-1] > array[middle] && array[middle+1] > array[middle]
      #if prev element > middle and next < middle
      #return middle
      # if prev element < middle and next > middle
      if array[middle-1] < array[middle] 
        #recursive function middle = start and end
        find_min(array, start, middle-1)
      end
    elsif array[middle] < array[start] && array[middle] < array[last]
    # middle is less than both
      #check the prev element of middle and the next element
        return array[middle] if array[middle-1] > array[middle]
      #if prev element > middle and next < middle
      #return middle
      # if prev element < middle and next > middle
        #recursive function middle = end and start
end
```
