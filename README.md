# snake-water-gun-game-in-c
#include <stdio.h>
#include<time.h>
#include<stdlib.h>

int SnakeWaterGun(char you,char comp)
{
//returns 1 if you win,-1 if you lose and 0 if draw
//condition draw
//cases covered
//ss
//gg
//ww

    if(you==comp)
    {
        return 0;
    }
    
    
  //non-draw condition
  //condition covered
  //sg
  //gs
  //sw
  //ws
  //gw
  //wg
  
    if(you=='s' && comp=='g')
    {
        return -1;
    }
    else if(you=='g' && comp=='s')
    {
        return 1;
    }
    
    
    if(you=='s' && comp=='w')
    {
        return 1;
    }
    else if(you=='w' && comp=='s')
    {
        return -1;
    }
    
    if(you=='g' && comp=='w')
    {
        return -1;
    }
    else if(you=='w' && comp=='g')
    {
        return 1;
    }
}
int main() {
   char you,comp;
   srand(time(0));
   int number=rand()%100+1;
   if(number <33)
   {
       comp='s';
   }
   else if(number >33 && number<66)
   {
       comp='w';
   }
   else
   {
       comp='g';
   }
    
   if("enter s for snake,w for water and g for gun\n");
   scanf("%c",&you);
   int result=SnakeWaterGun(you,comp);
   printf("you chose %c and computer chose %c\n",you,comp);
   if(result==0)
   {
       printf("game draw\n");
   }
   else if(result==1)
   {
       printf("you win!\n");
   }
   else
   {
       printf("you lose!\n");
   }
    return 0;
}
/*OUTPUT:
s
you chose s and computer chose w
you win!
*/
