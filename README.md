# Memory Allocator Algorithm CP386
## Description
In this algorithm, first fit, best fit, and worst fit are used for contiguous memory allocation. It involves managing contiguous region of memory size MAX where addresses may range from 0...MAX-1. 
- First fit. Allocate the first hole that is big enough. Searching can start either at the beginning of the set of holes or at the location where the previous first-fit search ended. We can stop searching as soon as we find a free hole that is large enough.

- Best fit. Allocate the smallest hole that is big enough. Search the entire list, unless the list is ordered by size. This strategy produces the smallest leftover hole.

- Worst fit. Allocate the largest hole. Again, search the entire list, unless it is sorted by size. This strategy produces the largest leftover hole, which may be more useful than the smaller leftover hole from a best-fit approach.
