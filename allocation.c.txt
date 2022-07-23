/*
 * Name: Alexandros Ioannou
 * ID: 191699620
 *
 * In this program, first fit, best fit, and worst fit are used for contiguous memory allocation.
 * It involves managing contiguous region of memory size MAX where addresses may range from 0...MAX-1
 * Unfortunately, I have not been able to implement the code successfully so I will try my best and
 * write the algorithm in plain english and some pseudocode of how I would have implemented the code
 * in hope of some part marks on this assignment
 */


/*
 * Request for a contiguous block of memory:
 * If "RQ" is inputed this algorithm will execute
 * Since each process is contained in a single contiguous block of memory, memory is divided into several fixed size partitions
 * In this case, each partition contains one process exactly
 * In this function, the input of the user is checked in order to execute an algorithm accordingly
 * If "F", first fit algorithm is executed
 * If "B", best fit algorithm is executed
 * If "W", worst fit algorithm is executed
 *
 * Release of a contiguous block of memory:
 * If "RL" is inputed this algorithm will execute
 * When these processes are terminated, memory is released/freed
 * This creates holes, which are the free blocks of memory
 * As mentioned above, here the holes will be searched in order to determine which hole is best to allocate
 *
 * Report the regions of free and allocated memory:
 * If "Status" is inputed this algorithm will execute
 * To create a status report a loop will be created to search through the queue/list (while pointer->next !=null)
 * Then it can be printed accordingly using node pointers, pointing to the next starting address, next ending address and the next process id
 *
 */

void firstFit() {

	/* First fit algorithm description:
	 * Initializes memory blocks and processes with size.
	 * Initialize them as free blocks
	 * Checks if each process can be assigned to the current block
	 * Checks if the size of process is less than the size of the block in order to make the assignment and move on the next process
	 * If the previous check is false, moves on to the rest of the blocks
	 *
	 * Steps:
	 * 1. Two indexes will be initialized (i,j) in order to loop through
	 * the number of processes and the number of blocks available.
	 * An array will be initialized as well in order to store the block IDs.
	 * Initially no blocks are assigned to any process
	 *
	 * 2. A loop would be created to loop through the number of processes with index i.
	 * A nested loop will also be created to loop through the number of blocks available with index j.
	 * Inside these loops each process will be picked and find the suitable blocks
	 * according to its size and assign to it.
	 *
	 * 3. Inside the nested loop, we will check if the block size at index j is greater or equal to the process size at index i.
	 * If true, then the block available at index j will be allocated/assigned to the ith process.
	 * 		Once assigned, the block size will be reduced by subtracting it by the process size. This reduces the available memory in the block.
	 * 		Then break the if statement in order to move to the next process in the queue
	 *
	 * 4. Check if 'F' was entered by the user and print the first fit algorithm processes accordingly
	 * If there is insufficient memory to allocate to a request, it will output an error message and reject the request, and put the process in a waitng queue
	 */
}

void bestFit(){
	/*
	 * Best fit algorithm description:
	 * Initializes memory blocks and processes with size.
	 * Initialize them as free blocks
	 * Each process is picked and assigned to the MINIMUM block size depending on the process size.
	 * Example: min(blockSize[1], blockSize[2],.....blockSize[n]) > processSize[current], if found then assign it to the current process.
   	 * If it cannot be assigned, move on to the rest of the processes.
   	 *
   	 * Steps:
	 * 1. Two indexes will be initialized (i,j) in order to loop through
	 * the number of processes and the number of blocks available.
	 * An array will be initialized as well in order to store the block IDs.
	 * Initially no blocks are assigned to any process
	 *
	 * 2. A loop would be created to loop through the number of processes with index i.
	 * Inside this loop before the nested loop, an index will be initialized to -1(null) to keep track of the best fit block for the current process (bfindex)
	 * 		A nested loop will also be created to loop through the number of blocks available with index j.
	 * Inside these loops each process will be picked and find the suitable blocks
	 * according to its size and assign to it.
	 *
	 * 3. Inside the nested loop, we will check if the block size at index j is greater or equal to the process size at index i.
	 * If true
	 * 		We check if the bfindex is null (if no block was found for the current process), if it is then index j, which holds the index for the number of blocks, is assigned to bfindex
	 * 		Else if, we would check if the block size at index bfindex is GREATER than the block size at the current index (j). This is finding the MINIMUM block size.
	 * 		If true, we assign the current index (j) to bfindex
	 * Now, we check if a block was found for the current process, in other words if bfindex is not equal to -1 (null)
	 * 		Memory allocation will take place where the block available at index j will be allocated/assigned to the bfindexth process
	 * 		Once assigned, the block size will be reduced by subtracting it by the process size. This reduces the available memory in the block.
	 *
	 * 4. Check if 'B' was entered by the user and print the best fit algorithm processes accordingly
	 * If there is insufficient memory to allocate to a request, it will output an error message and reject the request, and put the process in a waitng queue
	 */
}

void worstFit(){
	/*
	 * Worst fit algorithm description:
	 * Initializes memory blocks and processes with size.
	 * Initialize them as free blocks
	 * Each process is picked and assigned to the MAXIMUM block size depending on the process size.
	 * Example: max(blockSize[1], blockSize[2],.....blockSize[n]) > processSize[current], if found then assign it to the current process.
   	 * If it cannot be assigned, move on to the rest of the processes.
   	 *
   	 * Steps:
	 * 1. Two indexes will be initialized (i,j) in order to loop through
	 * the number of processes and the number of blocks available.
	 * An array will be initialized as well in order to store the block IDs.
	 * Initially no blocks are assigned to any process
	 *
	 * 2. A loop would be created to loop through the number of processes with index i.
	 * Inside this loop before the nested loop, an index will be initialized to -1(null) to keep track of the best fit block for the current process (bfindex)
	 * 		A nested loop will also be created to loop through the number of blocks available with index j.
	 * Inside these loops each process will be picked and find the suitable blocks
	 * according to its size and assign to it.
	 *
	 * 3. Inside the nested loop, we will check if the block size at index j is greater or equal to the process size at index i.
	 * If true
	 * 		We check if the wfindex is null (if no block was found for the current process), if it is then index j, which holds the index for the number of blocks, is assigned to bfindex
	 * 		Else if, we would check if the block size at index wfindex is LESS than the block size at the current index (j). This is finding the MAXIMUM block size.
	 * 		If true, we assign the current index (j) to wfindex
	 * Now, we check if a block was found for the current process, in other words if wfindex is not equal to -1 (null)
	 * 		Memory allocation will take place where the block available at index j will be allocated/assigned to the wfindexth process
	 * 		Once assigned, the block size will be reduced by subtracting it by the process size. This reduces the available memory in the block.
	 *
	 * 4. Check if 'W' was entered by the user and print the worst fit algorithm processes accordingly
	 * If there is insufficient memory to allocate to a request, it will output an error message and reject the request, and put the process in a waitng queue
	 */
}

