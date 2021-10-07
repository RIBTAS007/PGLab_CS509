# PG LAB (CS509)

## Assignment 3

In this project, you would be developing an implementation of Grid files for storing and querying 2-dimensional data points.

### Dataset for evaluation:

We would be using synthetic datasets for evaluation. Each data point in the dataset is a triple defined as follows: 

    <id> <x-coordinate> <y-coordinate>. 
  
Here **\<id\>** is a unique number between 1 and number-points-in-dataset. 
**Note** : the spatial coordinates of the points in the datasets could be repeated. In other words, two different data-points (i.e., two different **id**s can have the same **x** and **y** coordinates.

**Dataset A**: 30000 points generated in a uniformly random fashion where the **x** and **y** coordinates are random integers between 0 and 400.

### Index structures need to be implemented:

1. **Grid files** Please refer to the notes on this topic.

### Simulating Buckets:

Buckets are to be implemented as text files in your code. Bucket size is defined as the number of data points it
can accommodate. For instance, if the bucket-size is defined to be 30, it means that the file simulating the bucket
can store 30 data records. 

**Very Imp**: Bucket sizes must be taken as input, should not be hard coded. The value of bucket-size would be varied in the experiments.

### Query Algorithm to be implemented on index structures:

**Range query on GRID files**: Given the lower left and the upper right coordinates of a query rectangle, retrieve
all points which fall inside the rectangle. Correctness of the algorithm must be ensured. Grossly inefficient
techniques and naive solutions would not be accepted.

### Implementation specifications:

1.  Input dataset should be read from a file.

2.  Buckets must be shared whenever necessary and the splits must be axis parallel lines, i.e., they must be through and throughout.
  
3.  Points should be inserted one by one into the Grid file. Your code should have a separate function for insertion. Also, there should be separate functions for splitting the scales and splitting the buckets. You may choose to split at the median data point (choice of axis is up to you). Appropriate implementation logic should be present for rearrangement of buckets.
 
4.  Your implementation should have appropriate global data structures for the following: 
    1.  X and Y scales which denote the current grid structure (i.e., the split points on x and y axis).
    2.  A “mapper” which maps a grid cell to a bucket.
 
5.  Your implementation should have appropriate print functions for the Grid files. This function should print the entire data structure and the bucket contents. Your TA will use this function to evaluate the correctness of your code on small datasets. Output of this print function should be comprehensive and formatted
appropriately. Scalability testing would be done on large datasets.
 
6.  In addition to the range query algorithm on Grid files, also implement a naive approach for solving range queries which just traverses through the dataset to return the points which are inside the query rectangle. TThishis function should be used to evaluate the correctness of your range query algo on Grid files.

### Solution 

0.  Use [genetare_input.o](genetare_input.o) to generate random 'N' sample input in [input.txt](input.txt) file

1.  Execute [Project.o](Project.o) file and make sure input.txt file is also present in the same folder.

2.  It will ask to enter the size of bucket

    eg: Enter  size of bucket :=101

    further on executing it will ask the inputs for bottom left and top right cordinates of query region(rectangle) and you can give two space sperated values.

    eg: 
        bottom left point : 100 5   
        upper right point : 300 300
    
3. After execution it will generate the buckets that are the physical space containing the desired points.
   Also in terminal the output will be printed as follows

       list of bucket  --> 13
       15  16  17  18  19  20  21  22  24  25  26  28  30
       out put of query -->
       3379
       
4. to confirm whether the outputs are correct or not , we have created [test_output.o](test_output.o) which find the solution using brute force, comapares the above result with that of brute force approach and tells whether the output is correct or not.

5. So after executing project.out , 
   a. change the values of Q.x1 and Q.x2 with the same values as that of bottom left corner and top rigjht corner respectively.
   b. save the file
   c. execute the file using 
         
         ./test_output.out
      
6. If our answer is correct , then it will print "correct output" on the terminal.


