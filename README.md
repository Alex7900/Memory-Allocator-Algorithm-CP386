# Memory Allocator Algorithm CP386
## Description
THIS IS NOT A FULL IMPLEMENTATION. In this algorithm, first fit, best fit, and worst fit are used for contiguous memory allocation. It involves managing contiguous region of memory size MAX where addresses may range from 0...MAX-1.
- First fit: Allocate the first hole that is big enough. Searching can start either at the beginning of the set of holes or at the location where the previous first-fit search ended. We can stop searching as soon as we find a free hole that is large enough.

- Best fit: Allocate the smallest hole that is big enough. Search the entire list, unless the list is ordered by size. This strategy produces the smallest leftover hole.

- Worst fit: Allocate the largest hole. Again, search the entire list, unless it is sorted by size. This strategy produces the largest leftover hole, which may be more useful than the smaller leftover hole from a best-fit approach.

## How to Use
The program responds to the following commands:
- RQ (request)
- RL (release) 
- C (compact)
- Status (status report)
- Exit (exit)

If implemented correctly, once the program has started, the user will be presented with the following:
**command>**
From here the user will enter one of the commands above to execute the memory allocator

A request for 20,000 bytes will appear as follows:

*command>RQ P0 20000 B*  
The first parameter to the RQ command is the new process that requires the memory, followed by the amount of memory being requested, and finally the strategy. (In this situation, “B” refers to best fit.)  
The RQ flags are:
- F-First fit

- B-Best fit

- W-Worst fit

Similarly, a release will appear as:  
*command>RL P0*   
This command will release the memory that has been allocated to process P0. The command for compaction is entered as:

*command>C*  
This command will compact unused holes of memory into one region.

Finally, the Status command for reporting the status of memory is entered as:  
*command>Status*  
Given this command, the program will report the regions of memory that are allocated and the regions that are unused. 

## Sample Output
![image](https://user-images.githubusercontent.com/96122498/180584662-28648fa3-4a77-4445-907c-aff649c64f0a.png)

## Authors
- Alexandros Ioannou, 191699620

