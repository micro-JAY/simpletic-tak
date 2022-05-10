import itertools
grid = "         "
grid_matrix = [[grid[0], grid[1], grid[2]],
               [grid[3], grid[4], grid[5]],
               [grid[6], grid[7], grid[8]]]
game_state = [" ", " ", " ", " ", " ", " ", " ", " ", " "]

def print_board():
    print('---------')
    print('|', grid_matrix[0][0], grid_matrix[0][1], grid_matrix[0][2], '|')
    print('|', grid_matrix[1][0], grid_matrix[1][1], grid_matrix[1][2], '|')
    print('|', grid_matrix[2][0], grid_matrix[2][1], grid_matrix[2][2], '|')
    print('---------')
    
def xwins(x):
    if game_state[2] == game_state[4] == game_state[6] == "X" or game_state[0] == game_state[4] == game_state[8] == "X" or \
        game_state[0] == game_state[1] == game_state[2] == "X" or game_state[3] == game_state[4] == game_state[5] == "X" or \
        game_state[6] == game_state[7] == game_state[8] == "X" or game_state[0] == game_state[3] == game_state[6] == "X" or \
        game_state[1] == game_state[4] == game_state[7] == "X" or game_state[2] == game_state[5] == game_state[8] == "X":
        return True
def owins(x):
    if game_state[2] == game_state[4] == game_state[6] == "O" or game_state[0] == game_state[4] == game_state[8] == "O" or \
        game_state[0] == game_state[1] == game_state[2] == "O" or game_state[3] == game_state[4] == game_state[5] == "O" or \
        game_state[6] == game_state[7] == game_state[8] == "O" or game_state[0] == game_state[3] == game_state[6] == "O" or \
        game_state[1] == game_state[4] == game_state[7] == "O" or game_state[2] == game_state[5] == game_state[8] == "O":
        return True
def update():
    global game_state # has to be global in order to update from game function
    game_state = list(itertools.chain.from_iterable(grid_matrix))

def game():
    global game_state
    x_turn = True
    o_turn = False
    while True:
        while x_turn is True:
            x, y = input("Enter the coordinates: ").split()
            if x.isdigit() and y.isdigit():
                x = int(x) - 1
                y = int(y) - 1
                if not ((x >= 0 and x <= 2) and (y >= 0 and y <= 2)):
                    print("Coordinates should be from 1 to 3!")
                else:
                    if grid_matrix[x][y] == '_' or " ":
                        grid_matrix[x][y] = 'X'
                        update()
                        print_board()
                        if xwins(game_state) is True:
                            print("X wins")
                            exit()
                        elif game_state.count(" ") == 0:
                            print("Draw")
                            exit()
                        else:
                            x_turn = False
                            o_turn = True
                            break
                    else:
                        print('This cell is occupied! Choose another one!')
            else:
                print('You should enter numbers!')
                
        while o_turn is True:
            x, y = input("Enter the coordinates: ").split()
            if x.isdigit() and y.isdigit():
                x = int(x) - 1
                y = int(y) - 1
                if not ((x >= 0 and x <= 2) and (y >= 0 and y <= 2)):
                    print("Coordinates should be from 1 to 3!")
                else:
                    if grid_matrix[x][y] == '_' or " ":
                        grid_matrix[x][y] = 'O'
                        update()
                        print_board()
                        if owins(game_state) is True:
                            print("O wins")
                            exit()
                        elif game_state.count(" ") == 0:
                            print("Draw")
                            exit()                        
                        else:
                            o_turn = False
                            x_turn = True
                            break
                    else:
                        print('This cell is occupied! Choose another one!')
            else:
                print('You should enter numbers!')

print_board()
game()
