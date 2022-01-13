# cse210-01
CSE 210
#   Stephanie Peña
#   Tic-Tac-Toe



def main():
    #create board and player as variables
    board = create()
    player = next_player("")
  
    #use while to execute a set of statements and or 
    # to connect two expressions into one compound expression
    while not (winner(board) or is_a_draw(board)):
        display_board(board)
        make_move(player, board)



        player = next_player(player)
    display_board(board)
    #use enhanced input validation 
    print("Great game!") 


def create():
    #use enhanced input validation 
    board = []
    for square in range(9):
        board.append(square + 1)
    return board

def display_board(board):

    print()
    print(f"{board[0]}|{board[1]}|{board[2]}")
    print('-+-+-')
    print(f"{board[3]}|{board[4]}|{board[5]}")
    print('-+-+-')
    print(f"{board[6]}|{board[7]}|{board[8]}")
    print()
    
def is_a_draw(board):
    for square in range(9):

        if board[square] != "x" and board[square] != "o":
    #use drawn board as guide for players
            return False
    return True 
    


def winner(board):
    return (board[0] == board[1] == board[2] or board[3] == board[4] == board[5] or board[6] == board[7] == board[8] or board[0] == board[3] == board[6] or board[1] == board[4] == board[7] or
            board[2] == board[5] == board[8] or board[0] == board[4] == board[8] or board[2] == board[4] == board[6])

def make_move(player, board):


    square = int(input(f"{player}'s turn to choose (1-9): "))
    board[square - 1] = player
def next_player(current):
    if current == "" or current == "o":
        return "x"
    elif current == "x":
        return "o"




if __name__ == "__main__":
    main()
