# Chess
![Magnus with the white pieces playing Nepo with the Black pieces](https://en.chessbase.com/portals/all/2022/02/airthings/08/carlsen-nepo-dubai.jpeg)
## More of thoughts than actions
### Opening
### Middlegame
### Endgame

# CHESS GAME WITH PYTHON
```
class ChessBoard:
    def __init__(self):
        self.board = [['R', 'N', 'B', 'Q', 'K', 'B', 'N', 'R'],
                      ['P', 'P', 'P', 'P', 'P', 'P', 'P', 'P'],
                      [' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
                      [' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
                      [' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
                      [' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '],
                      ['p', 'p', 'p', 'p', 'p', 'p', 'p', 'p'],
                      ['r', 'n', 'b', 'q', 'k', 'b', 'n', 'r']]

    def print_board(self):
        for row in self.board:
            print(" ".join(row))

    def move_piece(self, start, end):
        start_row, start_col = start
        end_row, end_col = end
        piece = self.board[start_row][start_col]
        self.board[start_row][start_col] = ' '
        self.board[end_row][end_col] = piece

def get_coordinates(move):
    col_map = {'a': 0, 'b': 1, 'c': 2, 'd': 3, 'e': 4, 'f': 5, 'g': 6, 'h': 7}
    start_col = col_map[move[0]]
    start_row = 8 - int(move[1])
    end_col = col_map[move[2]]
    end_row = 8 - int(move[3])
    return (start_row, start_col), (end_row, end_col)

def main():
    board = ChessBoard()
    board.print_board()

    while True:
        move = input("Enter your move (e.g., 'a2a4'): ")
        if move == 'exit':
            break
        start, end = get_coordinates(move)
        board.move_piece(start, end)
        board.print_board()

if __name__ == "__main__":
    main()

```
