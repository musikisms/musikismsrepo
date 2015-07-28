import time

# Game-of-life-like interface

print "Welcome to the Game of Life."

# Initialising grid
print "Initialising grid."
print "Please enter grid length."
gridLength = int(raw_input("> "))
print "Please enter grid height."
gridHeight = int(raw_input("> "))

gridArray = {}

for n in range(0, gridHeight):
	for m in range(0, gridLength):
		gridArray[m,n] = 'x'

print "Grid initialised."
# print gridArray

# Print map
# Print first line (x-coords)
def printFirstLine():
	"""Prints x-coordinates of map"""
	teststring0 = "   " 
	for m in range (0, gridLength):
		printNumber = m + 1
		teststring0 += '%s ' % printNumber
	print teststring0
# Generic line print function
def printLine(n):
	"""Print line 'n' of gridArray"""
	linenumber = n + 1
	#teststring = '%s| ' % linenumber
	teststring = ""
	for m in range(0, gridLength):
		teststring += '%s ' % gridArray[m,n]
	print teststring
# Generic print map function
def printmap():
	"""Prints whole map"""
	# Print map x-coords
	#printFirstLine()	
	# Print all lines of map
	for n in range (0, gridHeight):
		printLine(n)


# Define functions that checks squares next to current gridpoint
# in all eight cardinal directions.
# If square = 'x', return True.

def checkE(m,n):
	"""Checks grid to the right if it's x or o. If  x, return TRUE."""
	nextsquare = m + 1
	if nextsquare < gridLength:
		if gridArray[nextsquare,n] == 'x':
			return True
		else:
			return False
	else:
		return False
		
def checkN(m,n):
	"""Checks grid to the top if it's x or o. If  x, return TRUE."""
	upsquare = n - 1
	if upsquare >= 0:
		if gridArray[m,upsquare] == 'x':
			return True
		else:
			return False
	else:
		return False
		
def checkS(m,n):
	"""Checks grid to the bottom if it's x or o. If  x, return TRUE."""
	downsquare = n + 1
	if downsquare < gridHeight:
		if gridArray[m,downsquare] == 'x':
			return True
		else:
			return False
	else:
		return False
		
def checkW(m,n):
	"""Checks grid to the left if it's x or o. If  x, return TRUE."""
	prevsquare = m - 1
	if prevsquare >= 0:
		if gridArray[prevsquare,n] == 'x':
			return True
		else:
			return False
	else:
		return False

def checkNW(m,n):
	"""Checks grid to the northwest if it's x or o. If  x, return TRUE."""
	backsquare = m - 1
	upsquare = n - 1
	if backsquare >= 0 and upsquare >= 0:
		if gridArray[backsquare, upsquare] == 'x':
			return True
		else:
			return False
	else:
		return False

def checkNE(m,n):
	"""Checks grid to the northeast if it's x or o. If  x, return TRUE."""
	frontsquare = m + 1
	upsquare = n - 1
	if frontsquare < gridLength and upsquare >= 0:
		if gridArray[frontsquare, upsquare] == 'x':
			return True
		else:
			return False
	else:
		return False

def checkSE(m,n):
	"""Checks grid to the southeast if it's x or o. If  x, return TRUE."""
	frontsquare = m + 1
	downsquare = n + 1
	if frontsquare < gridLength and downsquare < gridHeight:
		if gridArray[frontsquare, downsquare] == 'x':
			return True
		else:
			return False
	else:
		return False

def checkSW(m,n):
	"""Checks grid to the southwest if it's x or o. If  x, return TRUE."""
	backsquare = m - 1
	downsquare = n + 1
	if backsquare >= 0 and downsquare < gridHeight:
		if gridArray[backsquare, downsquare] == 'x':
			return True
		else:
			return False
	else:
		return False

def checkAll(m,n):
	"""Checks grid to N, S, E, W around current gridpoint."""
	right = checkE(m,n)
	left = checkW(m,n)
	up = checkN(m,n)
	down = checkS(m,n)
	if right and left and up and down:
		return True
	else:
		return False

def changer(a,b):
	"""If squares to N, S, E, W around gridpoint are 'x', change current gridpoint to 'o'"""
	if checkAll(a,b) == True:
		gridArray[a,b] = ' '
	else:
		return False

def iterator():
	"""ITERATE"""
	m = 0
	n = 0
	for n in range(0, gridHeight):
		for m in range(0, gridLength):
			changer(m,n)
	printmap()

print "Initiating initial initialiser."

iterator()

def neighbours(m,n):
	"""Check number of live neighbours, indicated by 'x'"""
	around = 0
	if checkN(m,n) == True: 
		around += 1
	if checkS(m,n) == True:
		around += 1
	if checkW(m,n) == True:
		around += 1
	if checkE(m,n) == True:
		around += 1
	if checkNW(m,n) == True:
		around += 1
	if checkNE(m,n) == True:
		around += 1
	if checkSE(m,n) == True:
		around += 1
	if checkSW(m,n) == True:
		around += 1
	return around

def amAlive(m,n):
	if gridArray[m,n] == 'x':
		return True
	else:
		return False

def GOLrules(m,n):
	neigh = neighbours(m,n)
	if amAlive(m,n) == True:
		if neigh < 2:
			gridArray[m,n] = ' '
		elif neigh > 3:
			gridArray[m,n] = ' '
		else:
			return False
	else:
		if neigh == 3:
			gridArray[m,n] = 'x'
			
		
def GOLiterator():
	"""Game of life"""
	# DO IT	
	m = 0
	n = 0
	for n in range(0, gridHeight):
		for m in range(0, gridLength):
			GOLrules(m,n)
	printmap()	

# Yesterday you said tomorrow but now it's TODAY.

print "Ready to proceed."
print "Enter number of iterations to perform."
i = raw_input("> ")
count = 1

while count <= int(i):
	print count
	GOLiterator()
	count += 1
	time.sleep(0.01)
	

