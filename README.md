import java.util.*;

public class TicTacToe
{
    
    public static void main(String[]args)
    {
      
        System.out.println("Welcome to Tic Tac Toe .....");
        char[] board = new char[] {'-','-','-','-','-','-','-','-','-'}; 
        System.out.println("USER1 starts with X");
        System.out.println("USER2 starts with O");
    
    int i=0;
    int j=1;
    int k=1;
    boolean gameover=false;
   
    while(i<board.length)
    {
      while(j<=5&&gameover!=true)
      {
        int player1=GetInteger("Enter the slot number to place X");
        if(player1>9)
        {
          System.out.println("INVALID INPUT please enter the slot number between 1 to 9");
          continue;
          
        }
        if(board[player1-1]=='-')
        {
          board[player1-1]='X';
          j++;
          i++;
          board(board);
          break;     
        }
        else
        {
          System.out.println("The slot alredy filed please choose another slot");
          continue;
        }
       }
       boolean xwin=check_x_winner(board);
            if(xwin==true)
            {
              System.out.println("Player 1 wins.....");
              gameover=true;
              break;
            }
      while(k<=4 &&gameover!=true)
      {
        int player2=GetInteger("Enter the slot number to place O");
        if(player2>9)
        {
          System.out.println("INVALID INPUT please enter the slot number between 1 to 9");
          continue;
          
        }
        if(board[player2-1]=='-')
        {
          board[player2-1]='O';
          board(board);
          k++;
          i++;
          break;
        }
        else
        {
          System.out.println("The slot alredy filed please choose another slot");
          continue;
        }
      }
      boolean owin=check_o_winner(board);
      if(owin==true)
      {
        System.out.println("Player 2 wins.....");
        gameover=true;
        break;
      }
      
    }    
    if(gameover!=true)
    {
      System.out.println("DRAW");
    }  
  }
   
   public static void board(char[]board)
   {
     System.out.println( board[0]+" | "+board[1]+" | "+board[2] );
     System.out.println("--+---+---");
     System.out.println(board[3]+" | "+board[4]+" | "+board[5]);
     System.out.println("--+---+---");
     System.out.println(board[6]+" | "+board[7]+" | "+board[8]);
   }

   public static int GetInteger(String message)
   {
    System.out.println(message);
    Scanner sc = new Scanner(System.in);
    int temp = sc.nextInt();
    return temp ;
}
public static  boolean check_x_winner(char[]board)
{
  boolean xwinner=false;
    if(board[0]=='X'&&board[1]=='X'&&board[2]=='X'||board[3]=='X'&&board[4]=='X'&&board[5]=='X'||board[6]=='x'&&board[7]=='X'&&board[8]=='X'||board[0]=='X'&&board[3]=='X'&&board[6]=='X'||board[1]=='X'&&board[4]=='X'&&board[7]=='X'||board[2]=='X'&&board[5]=='X'&&board[8]=='X'||board[0]=='X'&&board[4]=='X'&&board[8]=='X'||board[6]=='X'&&board[4]=='X'&&board[2]=='X')
         {
              xwinner=true;
         } 
         return xwinner;
}
public static boolean check_o_winner(char[]board)
{
  boolean owinner=false;
  if(board[0]=='O'&&board[1]=='O'&&board[2]=='O'||board[3]=='O'&&board[4]=='O'&&board[5]=='O'||board[6]=='O'&&board[7]=='O'&&board[8]=='O'||board[0]=='O'&&board[3]=='O'&&board[6]=='O'||board[1]=='O'&&board[4]=='O'&&board[7]=='O'||board[2]=='O'&&board[5]=='O'&&board[8]=='O'||board[0]=='O'&&board[4]=='O'&&board[9]=='O'||board[6]=='O'&&board[4]=='O'&&board[2]=='O')
         {
           owinner=true;
         } 
         return owinner;
} 


}
