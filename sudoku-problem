board = [[9,3,0,0,0,0,0,8,0],
         [5,0,0,0,0,4,0,0,0],
         [0,0,0,3,6,0,2,0,0],
         [0,0,0,1,0,0,0,9,7],
         [0,0,0,0,0,0,4,0,0],
         [6,0,2,0,0,0,0,0,0],
         [0,0,0,0,3,0,6,0,0],
         [4,0,3,5,0,0,0,0,0],
         [0,7,0,0,0,9,5,1,0]]

# Function to print board
def print_board(bo):
    for i in range(len(bo)):
        if i % 3 == 0 and i != 0:
            print("-"*32)
        for j in range(len(bo[0])):
            if j % 3 == 0 and j != 0:
                print("|" + " ", end = " ")
            if j == 8:
                print(bo[i][j])
            else:
                print(str(bo[i][j]) + " ", end = " ")

# Check if the input is valid
def check_valid(row,column,num,bo):
    for i in range(9): # Check row
        if bo[row][i] == num and i != column:
            return False

    for j in range(9): # Check column
        if bo[j][column] == num and j != row:
            return False

    x1 = column//3
    y1 = row//3
    for x2 in range(x1*3, (x1*3)+3): # Check grid
        for y2 in range(y1*3, (y1*3)+3):
            if bo[y2][x2] == num:
                return False
    return True

# Function to solve the sudoku
def solve(bo):
    for i in range(9):
        for j in range(9):
            if bo[i][j] == 0:
                for n in range(1,10):
                    if check_valid(i,j,n,bo):
                        bo[i][j] = n
                        solve(bo)
                        bo[i][j] = 0
                return
    print_board(bo)

solve(board)
