---
layout: post
title:  "Striver SDE Sheet Solutions"
date:   2021-01-09 
category: tech
tags: 
- Interview Preparation
- Data Structures
- Algorithms 
---
This post contains solutions to the problems in the Striver Sheet along with explanations.
The sheet can be found [here.](https://takeuforward.org/interviews/strivers-sde-sheet-top-coding-interview-problems/)

## Day 1
### Set Matrix Zeros
Link to the problem: <https://leetcode.com/problems/set-matrix-zeroes/>

#### The Problem Statement:
Given an **m x n** integer matrix matrix, if an element is 0, set its entire row and column to 0's, and return the matrix.

You must do it **in place**.

Constraints:
- O(1) Space Complexity

#### Approach:
We need to keep track of which rows and columns contain zeros. One way to do this is to keep row and column sets, which can keep track of the row and column numbers which contain 0.

*Time Complexity of this approach is **O(mn)** and space complexity is **O(m+n)**.*

We can optimise this approach by using the first row and column for markers of the remaining rows and columns. If a row or column contains a zero, we can mark the first element of the row or column as zero. Then we can traverse through the matrix and set the remaining elements of the marked row or column as zero.
Now for the cell ```matrix[0][0]```, it corresponds to both the first column and first row. We can use it to denote the first row and keep another extra variable to denote marker for the first column.

*Time complexity of this approach is **O(mn)** and space complexity **O(1)**.*

#### Code:
```cpp

void setZeroes(vector<vector<int>>& matrix) {
        //row and column dimensions
        int r = matrix.size();
        int c = matrix[0].size();
        //extra variable for first column
        bool is_col = false;
        
        //Iterate through every row
        for(int i=0; i<r; i++){
            if(matrix[i][0]==0) //Check if first column contains any zeros, if true then mark it
                is_col = true;
            
            //Iterate through every column except first column
            for (int j=1; j<c; j++){
                if(matrix[i][j]==0){ //Check if an element in a given cell is zero, if true then mark both the row and the column 
                    matrix[0][j]=0;
                    matrix[i][0]=0;
                }
            }
        }
        // Iterate through the matrix except first row and first column -> matrix[1:][1:]
        for(int i=1; i<r; i++)
            for(int j=1; j<c; j++){
                //Check whether either the row or column is marked, if true then set cell to zero
                if (!matrix[i][0] || !matrix[0][j])
                    matrix[i][j]=0;
            }
        
        // Check if first row is marked, if true then set all elements in first row to zero
        if(matrix[0][0]==0)
            for(int j = 0; j<c; j++){
                matrix[0][j]=0;
            }
        //Check if first column is marked, if true then set all elements in first column to zero       
        if(is_col)
            for(int i=0; i<r; i++){
                matrix[i][0]=0;
            }
        
        
    }


```