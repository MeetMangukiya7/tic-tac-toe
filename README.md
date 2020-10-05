# tic-tac-toe
Tic Tac Toe game made in javascript
""" below, there are spaces for you to add comments. You may want to add more comments than this, which is fine """

#draws board for tic-tac-toe import random def main(): boardsize = 3 #deleted inputBoardSize() #define board dimension board = defineBoard(boardsize) createBoardLabels(board, boardsize) drawBoard(board, boardsize) Player_1(board, boardsize) letter = '' ##### not my code

def Player_1(board, boardsize): elem = 'X' position = input('Player 1, enter number you want to play: ') print('Player 1, you are', elem, 'and you want to play Cell', position) for i in range(boardsize): for j in range(boardsize): # call on this code in player 1 if board[i][j] == int(position): board [i][j] = elem #update needs to find the input in the board and change it to X #if board[1][0] == input #board[1][0] = 'X'
if position != 'quit': print('Player, you entered', position) drawBoard(board, boardsize) if Win_Checker(board) != True: AI_Player(board, boardsize, moveList) else: print("Congratulations player 1, You win") def moveList (board, boardsize): moveList = [1, 2, 3, 4, 5, 6, 7, 8, 9]

def AI_Player(board, boardsize, moveList): movesToChoose = [] for i in range (boardsize): for j in range (boardsize): if type(board[i][j]) == int: movesToChoose.append(board[i][j]) move = random.choice(movesToChoose) for i in range (boardsize): for j in range (boardsize): if board [i][j] == int (move): board[i][j] = "O" print ('computer has entered',move) drawBoard(board, boardsize) Player_1 (board, boardsize)

def Player_2(board, boardsize): elem = '0' position = input('Player 2, enter number you want to play: ') print('Player 2, you are', elem, 'and you want to play Cell', position) if position != 'quit': print('Player, you entered', position) for i in range(boardsize): for j in range(boardsize): # call on this code in player 1 if board[i][j] == int(position): board [i][j] = elem drawBoard(board, boardsize) if Win_Checker(board) != True: Player_1(board, boardsize) else: print("Congratulations player 2, You win")

#def getPlayerMove(board): # Let the player type in his move.

move = ' '
while move not in '1 2 3 4 5 6 7 8 9'.split() or not isSpaceFree(board, int(move)): ###### not my code
  #  print('What is your next move? (1-9)')
   # move = input()
def defineBoard(boardsize): board = [[""] * boardsize for i in range(boardsize)] #make the basic (non-drawable) version of theboard print ('board in defineBoard is', board) return board

def inputBoardSize(): #this is so we can make a board of any dimension we like boardsize = input('enter board dimension: ') #not used in this version, but if it was, how? return int(boardsize)

def createBoardLabels(board, boardsize): # counter = 0 for i in range(boardsize): for j in range(boardsize): counter +=1 # call on this code in player 1 board[i][j] = counter print ('board in creatBoardLabels is', board) return (board)

def print_divider (boardsize): # print ('|'.join(['____' for x in range(boardsize)]))

def print_blank (boardsize): print ('|'.join([' ' for x in range(boardsize)])) #

def print_labels(counter, board, boardsize): # row = ' | '.join(['%2s' % board[counter][x] for x in range(boardsize)]) row = ' ' + row #if you want too get rid of the numbers then take out the + row in this line of code print(row)

def Win_Checker(board): if board[0][0]==board[0][1] and board[0][1]==board[0][2]: return True elif board[1][0]==board[1][1] and board[1][1]==board[1][2]: return True elif board[2][0]==board[2][1] and board[2][1]==board[2][2]: return True elif board[0][0]==board[1][0] and board[1][0]==board[2][0]: return True elif board[0][1]==board[1][1] and board[1][1]==board[2][1]: return True elif board[0][2]==board[1][2] and board[1][2]==board[2][2]: return True elif board[0][0]==board[1][1] and board[1][1]==board[2][2]: return True elif board[0][2]==board[1][1] and board[1][1]==board[2][0]: return True else: return False

def drawBoard(board, boardsize): # for i in range(boardsize): print_blank(boardsize) print_labels(i,board, boardsize) if (i == boardsize-1): print_blank(boardsize) else: print_divider(boardsize)

main() #run the program
