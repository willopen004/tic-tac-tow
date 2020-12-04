#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>
#include <math.h>

void undo_maker (int n, char array[n][n], int undo[2][n*n], int a, int turn)
{
    int j;
    a = abs (a);
    if (a > turn)
    {
        printf ("wrong move! try again!");
        return;
    }

        printf ("you were in turn: %d\n", turn);
        printf ("numbers of turns to return: %d\n", a);

    for (j=turn-1;j>=turn-a;j--)
    {
        printf ("row: %d, column: %d\n", undo[0][j], undo[1][j]);

        array [undo[0][j]-1][undo[1][j]-1] = '_';
    }
}
// this function will print the new board each turn
void board_maker (int n, char array[n][n])
{
    for (int row = 0; row < n; row++)
    {
        for (int column = 0; column < n; column++)
        {
            printf ("%c", array[row][column]);
        }
        printf ("\n");
    }
return;
}

// this function will check for a no winner
bool board_checker_no_win (int n, char array[n][n])
{
int row, column, boardcheck = 0;
for (column = 0; column<n; column++)
{
        for (row = 0; row<n; row++)
        {
            if (array[row][column] != '_')
            {
                boardcheck+=1;
            }
        }
}
        if (boardcheck == n*n)
        {
            printf ("game over! there is no winner!");
            return true;
        }

return false;
}
// this function will check for win in columns
bool board_checker_columns (int n, char array[n][n])
{
int row, column, Xcounter = 0, Ocounter = 0;
for (column = 0; column<n; column++)
{
        for (row = 0; row<n; row++)
        {
            if (array[row][column] == 'X')
            {
                Xcounter++;
            }
            if (array[row][column] == 'O')
            {
                Ocounter++;
            }
        }

        if (Xcounter == n)
        {
            printf ("player 1 wins!");
            return true;
        }
        if (Ocounter == n)
        {
            printf ("player 2 wins!");
            return true;
        }

        Xcounter = 0, Ocounter = 0;
}
return false;
}

// this function will check for win in rows
bool board_checker_rows (int n, char array[n][n])
{
int row, column, Xcounter = 0, Ocounter = 0;
for (row = 0; row<n; row++)
{
        for (column = 0; column<n; column++)
        {
            if (array[row][column] == 'X')
            {
                Xcounter++;
            }
            if (array[row][column] == 'O')
            {
                Ocounter++;
            }
        }

        if (Xcounter == n)
        {
            printf ("player 1 wins!");
            return true;
        }
        if (Ocounter == n)
        {
            printf ("player 2 wins!");
            return true;
        }

        Xcounter = 0, Ocounter = 0;
}
return false;
}


// this function will check for win in right diagonal
bool board_checker_diagonal_right (int n, char array[n][n])
{
int row, column, Xcounter = 0, Ocounter = 0;
for (column = 0; column<n; column++)
{
        for (row = 0; row<n; row++)
        {
            if (row == column)
            {
                if (array[row][column] == 'X')
                {
                    Xcounter++;
                }
                if (array[row][column] == 'O')
                {
                    Ocounter++;
                }
            }
        }

        if (Xcounter == n)
        {
            printf ("player 1 wins!");
            return true;
        }
        if (Ocounter == n)
        {
            printf ("player 2 wins!");
            return true;
        }
}
return false;
}
// this function will check for win in left diagonal
bool board_checker_diagonal_left (int n, char array[n][n])
{
int row =0, column =0, Xcounter = 0, Ocounter = 0;
for (column = n-1; column>=0; column--)
{


        if (array[row][column] == 'X')
        {
            Xcounter++;
        }
        if (array[row][column] == 'O')
        {
            Ocounter++;
        }


        if (Xcounter == n)
        {
            printf ("player 1 wins!");
            return true;
        }
        if (Ocounter == n)
        {
            printf ("player 2 wins!");
            return true;
        }

        row++;
}
return false;
}

// // this function will call the board checking functions
bool board_checker (int n, char array[n][n])
{

    if (board_checker_rows (n, array) == true)
    {
        printf ("\n1");
        return true;
    }

    if (board_checker_columns (n, array) == true)
    {
        printf ("\n2");
        return true;
    }

    if (board_checker_diagonal_right (n, array) == true)
    {
        printf ("\n3");
        return true;
    }

    if (board_checker_diagonal_left (n, array) == true)
    {
        printf ("\n4");
        return true;
    }

    if (board_checker_no_win (n, array) == true)
    {
        printf ("\n5");
        return true;
    }


return false;
}

// this function will set the players and the turns
void player_fun (int n, char array[n][n], int undo[2][n*n])
{
int row, column, turn = 0, player = 1;
do
{



printf ("\nplayer %d, enter next move:\n", player);

printf ("row: ");

scanf ("%d", &row);

if (row < 0)
{
    undo_maker (n, array, undo, row, turn);
    board_maker (n, array);
    continue;
}

printf ("column: ");

scanf ("%d", &column);

if (column < 0)
{
    undo_maker (n, array, undo, column, turn);
    board_maker (n, array);
    continue;
}

undo [0][turn] = row;
undo [1][turn] = column;
turn++;

    if (array[row-1][column-1] != '_' || row > n || column > n)
    {
        printf ("bad move, retry.");
        continue;
    }

    if (player == 1)
    {
        array[row-1][column-1] = 'X';
        player = 2;
    }
    else
    {
        array[row-1][column-1] = 'O';
        player = 1;
    }
board_maker (n, array);

} while (board_checker (n, array) == false);

}


int main()
{
int n=0;

printf ("please enter board size (1-10): ");

scanf ("%d", &n);

char array [n][n];

int undo[2][n*n];


// this for loop will set the board for the first time

for (int row = 0; row < n; row++)
    {
        for (int column = 0; column < n; column++)
        {
            array[row][column] = '_' ;
        }
    }

board_maker (n, array);
player_fun (n, array, undo);
    return 0;
}
