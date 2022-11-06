# Tic_tac-toe-in-C-C++
A simple and easy C/C++ tic tac toe game

## Code
```
#include <stdio.h> 
#include <stdlib.h>
#include <ctype.h>
#include <time.h>

char board[3][3];
const char PLAYER = 'X';
const char COMPUTER = 'O';


void resetBoard();
void printBoard();
int checkFreeSpaces();
void playerMove();
void computerMove();
char checkWinner();
void printWinner(char);


int main(){
    char winner = ' ';

    resetBoard();

    while(winner == ' ' &&checkFreeSpaces() != 0)
    {
        printBoard();

         playerMove();
        winner = checkWinner();
        if(winner != ' ' || checkFreeSpaces() == 0)
        {
            break;
        }

        computerMove();
        winner = checkWinner();
        if(winner != ' ' || checkFreeSpaces() == 0)
        {
            break;
        }   
    }

    printBoard();
    printWinner(winner);

    
    return 0;
}

void resetBoard(){
    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 3; j++)
        {
            board[i][j] = ' ';
        }
    }

}
void printBoard()
{
    printf("  %c| %c | %c ", board[0][0], board[0][1], board[0][2] );
    printf("\n---|---|---\n");
    printf("  %c| %c | %c  ", board[1][0], board[1][1], board[1][2] );
    printf("\n---|---|---\n");
    printf("  %c| %c | %c  ", board[2][0], board[2][1], board[2][2] );
    printf("\n---|---|---\n");
    printf("\n");

}

int checkFreeSpaces()
{
    int FreeSpaces = 9;

    for(int i = 0; i < 3; i++)
    {
        for(int j = 0; j < 3; j++)
        {
            if(board[i][j] != ' ')
            {
                FreeSpaces--;
            }
        }
    }
    return FreeSpaces;
}
void playerMove()
{
    int x;
    int y;

    do
    {
    printf(" Enter Row  #(1-3)");
    scanf("%d", &x);
    x--;
    printf(" Enter Column  #(1-3)");
    scanf("%d", &y);
    y--;

    if(board[x][y] != ' ')
    {
        printf("Invalid Move\n");
    }
    else
    {
        board[x][y] = PLAYER;
        break;
    }
    } while (board[x][y] != ' ');
     

}
void computerMove()
{
    // computer 
    srand(time(0));
    int x;
    int y;

    if(checkFreeSpaces() > 0)
    {
        do
        {
            x = rand() % 3;
            y = rand() % 3;
        } while (board[x][y] != ' ');
        
        board[x][y] = COMPUTER;
    }
    else
    {
        printWinner(' ');
    }
}
char checkWinner()
{
    for(int i = 0; i < 3; i++ )
    {
        if(board[i][0] == board[i][1] && board[i][0] == board[i][2])
        {
            return board[i][0];
        }
    }
    //check colums
        for(int i = 0; i < 3; i++ )
    {
        if(board[0][i] == board[1][i] && board[0][i] == board[2][i])
        {
            return board[0][i];
        }
    }
    //check diagonals
        for(int i = 0; i < 3; i++ )
    {
        if(board[0][0] == board[1][1] && board[0][0] == board[2][2])
        {
            return board[0][0];
        }
    }
        for(int i = 0; i < 3; i++ )
    {
        if(board[0][2] == board[1][1] && board[0][2] == board[2][0])
        {
            return board[0][2];
        }
    }
    return ' ';
}

void printWinner(char winner)
{
    if(winner == PLAYER)
    {
        printf("You Win");
    }
    else if(winner == COMPUTER)
    {
        printf("You Lose");
    }
    else
    {
        printf("It's a Tie");
    }
        printf("\nType Y/N to exit: \n");
        scanf("%s");
        if ("%s" == "Y")
        {
            printf(" \nThanks For Playing \n");
        }
        
        else if("%s" == "N")
        {
            printf("\nHope You Liked our game ?\n");
        }
        
        else
        {
            printf("\nInvalid Value\n");   
        } 
}
```
---
Thanks & Regards 
Ayushthepro111
follow me on twitter => [Click Here To Visit My Twitter And Follow Me](https://twitter.com/ayushma60129529)

##ScreenShots
![imgs](https://user-images.githubusercontent.com/103628088/200171465-60e8b9c9-6dfe-4a56-9425-c1655b054e9b.png)
![imgs](https://user-images.githubusercontent.com/103628088/200171514-01dfec8b-333e-40c0-842c-b20308404731.png)
<img width="670" alt="imgs" src="https://user-images.githubusercontent.com/103628088/200171548-9912a825-c5d8-4535-8122-753c88e8424a.png">
