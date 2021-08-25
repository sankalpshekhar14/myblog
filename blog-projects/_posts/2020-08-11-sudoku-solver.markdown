---
layout: post
title:  "Sudoku Solver"
date:   2020-08-11 
category: Projects
tags: 
- Python
- Backtracking 
---

I created a program for solving sudoku. The algorithm uses backtracking to find the correct combination of numbers in the puzzle.

A sudoku grid is a 9x9 matrix, with each box of 3x3 containing numbers from 1 to 9. There are two simple rules:

* No number in each columm or row should be repeated.
* Numbers in each 3x3 grid should not be repeated.

This is how an average sudoku grid looks like:

<img src="https://cdn.britannica.com/q:60/25/188725-050-C3DE2288/Sudoku-puzzles.jpg" width=300 height=300 title="A Sudoku Grid">

## The Algorithm

The goal is to fill all the unfilled boxes, by following the two rules. We use 9x9 nested lists, to represent the grid. The unfilled positions are initialised to zero.

```python
grid = [ [3, 0, 6, 5, 0, 8, 4, 0, 0], 
         [5, 2, 0, 0, 0, 0, 0, 0, 0], 
         [0, 8, 7, 0, 0, 0, 0, 3, 1], 
         [0, 0, 3, 0, 1, 0, 0, 8, 0], 
         [9, 0, 0, 8, 6, 3, 0, 0, 5], 
         [0, 5, 0, 0, 9, 0, 6, 0, 0], 
         [1, 3, 0, 0, 0, 0, 2, 5, 0], 
         [0, 0, 0, 0, 0, 0, 0, 7, 4], 
         [0, 0, 5, 2, 0, 6, 3, 0, 0],
]
```

The algorithm goes through all the blank positions. At the first blank position, it checks the possibility of a given number. If a number is possible, then it places it, and moves on to the next blank position. If we reach a point where no number is possible for the given blank space, the algorithm backtracks to the previous location and tries the next possible number. The program terminates, when there is no blank position left.

### The Code

* **findEmpty()** function traverses the grid and returns the first blank space.

```python
def findEmpty(): 					#Finds an empty space
	for i in range(9):
		for j in range(9):
			if(grid[i][j]==0):
				return i,j
```

* **checkPossibility(y,x,n)** takes the grid position(x,y) and number(n) as input, and checks if that number can be placed in that position.

```python
def checkPossibility(y,x,n):        #Checks if a given number can be filled in a given cell
	global grid
	x0=3*(x//3)
	y0=3*(y//3)
	for i in range(9):
		if(grid[i][x]==n):
			return False
	for i in range(9):
		if(grid[y][i]==n):
			return False
	for i in range(0,3):
		for j in range(0,3):
			if (grid[i+y0][j+x0] == n):
				return False
	
	return True
```
* **printBoard()** displays the grid in the correct format.

```python
def printBoard():    #Prints out the board
	global grid

	for i in range(len(grid)):
		if (i==0 or i%3==0):
			print('---------------------')
		for j in range(len(grid[0])):
			if (j%3==0 and j!=0):
				print('| ',end="")
			if(j==8):
				print(grid[i][j])
			else:
				print(str(grid[i][j])+ " ",end="")
	print('---------------------')
```
* **solveBoard()** is the recursive function that calls the above functions.

```python
def solveBoard():
	global grid                   #Solves the given board
	
	find=findEmpty()
	if not find:
		return True
	else:
		y,x=find
	
	for k in range(1,10):
		if(checkPossibility(y,x,k)):
			grid[y][x]=k
				#print(k)
			if solveBoard():
				return True
			grid[y][x]=0
		
	return False
```
More information on Backtracking can be found [here](https://en.wikipedia.org/wiki/Backtracking).