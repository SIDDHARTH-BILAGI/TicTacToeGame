# TicTacToeGame
It is a Tic Tac Toe Game which is built using C-Programming where there tic tac toe game is played between the software and the player. 

#include<stdio.h>
#include<stdlib.h>
 int chois(char a[10],int);
 int win(char a[9]);
 int big(char a[9]);
 main()
{
    int i,j,c,w,z;
    char a[9];
    printf("Enter number for incert\n");
    a[0]=' ';
    for(i=1;i<=9;i++)
    {
    a[i]=' ';
    printf("%d|",i);
    if(i%3==0)
    printf("\n");
    }
    for(i=1;i<=9;i++)
    {  
    if(i%2!=0)
    {
    printf("enter the your choice\n");
    scanf("%d",&c);
    z=c;
    if((c<10)&&(a[c-1]!='x'&&a[c-1]!='o'))
    {
    a[c-1]='x';
    for(j=0;j<9;j++)
    {
    printf("%c|",a[j]);
    if((j+1)%3==0)
    printf("\n");
    }
  //  default: printf("you loss the choice");
    } 
    w=win(a);
    if(w==0)
    {
    printf("player 2 is the winner 🏆");
    exit (0);
    }
    }else
    {
    printf("computer tern\n");
    z=chois(a,c);
   
    if(c<10)
    {
    a[z]='o';
    for(j=0;j<9;j++)
    {
    printf("%c|",a[j]);
    if((j+1)%3==0)
    printf("\n");
    }
   // default: printf("you loss the choice");
    }
    }
    w=win(a);
    if(w==0)
    {
    printf("player 1 is the winner 🏆");
    exit (0);
    }
    }
}
    int win(char a[9])
    {
    if(a[0]==a[1]&&a[1]==a[2]&&a[1]!=' ')
    return 0;
    if(a[3]==a[4]&&a[4]==a[5]&&a[5]!=' ')
    return 0;
    if(a[6]==a[7]&&a[7]==a[8]&&a[8]!=' ')
    return 0;
    if(a[0]==a[4]&&a[4]==a[8]&&a[0]!=' ')
    return 0;
    if(a[6]==a[4]&&a[4]==a[2]&&a[2]!=' ')
    return 0;
    if(a[0]==a[3]&&a[3]==a[6]&&a[0]!=' ')
    return 0;
    if(a[4]==a[1]&&a[1]==a[7]&&a[1]!=' ')
    return 0;
    if(a[2]==a[5]&&a[8]==a[2]&&a[2]!=' ')
    return 0;
    else 
    return 1;
    }
    int chois(char a[10],int x)
    {
    int m,y;
    y=big(a);
    if(y!=10)
    {
    m=y;
    return m;
    }
    else
    {
    switch(x)
    {
    case 1: 
    if (a[1]=='x'&&a[2]!='o')
    m=2;
    else if(a[2]=='x'&&a[1]!='o')
    m=1;
    else if(a[4]=='x'&&a[8]!='o')
    m=8;
     else if(a[8]=='x'&&a[4]!='o')
    m=4;
    else if(a[3]=='x'&&a[6]!='o')
    m=6;
    else if(a[6]=='x'&&a[3]!='o')
    m=3;
    else
    m=4;
    return m;
    case 2:
    if (a[0]=='x'&&a[2]!='o')
    m=2;
    else if(a[2]=='x'&&a[0]!='o')
    m=0;
    else if(a[4]=='x'&&a[7]!='o')
    m=7;
    else if(a[7]=='x'&&a[4]!='o')
    m=4;
    else
    m=5;
    return m;
    case 3: 
    if (a[1]=='x'&&a[0]!='o')
    m=0;
    else if(a[0]=='x'&&a[1]!='o')
    m=1;
    else if(a[4]=='x'&&a[6]!='o')
    m=6;
     else if(a[6]=='x'&&a[4]!='o')
    m=4;
    else if(a[5]=='x'&&a[8]!='o')
    m=8;
    else if(a[8]=='x'&&a[5]!='o')
    m=5;
    else
    m=4;
    return m;
    case 4: 
    if (a[4]=='x'&&a[5]!='o')
    m=5;
    else if(a[5]=='x'&&a[4]!='o')
    m=4;
    else if(a[6]=='x'&&a[0]!='o')
    m=0;
     else if(a[0]=='x'&&a[6]!='o')
    m=6;
    else
    m=4;
    return m;
    case 5: 
    if (a[1]=='x'&&a[7]!='o')
    m=7;
    else if(a[7]=='x'&&a[1]!='o')
    m=1;
    else if(a[5]=='x'&&a[3]!='o')
    m=3;
    else if(a[3]=='x'&&a[5]!='o')
    m=5;
    else if((a[0]=='x'&&a[8]!='o')||(a[7]=='x'&&a[5]=='x'))
    m=8;
    else if((a[2]=='x'&&a[6]!='o')||(a[7]=='x'&&a[3]=='x'))
    m=6;
    else if((a[6]=='x'&&a[2]!='o')||(a[5]=='x'&&a[1]=='x'))
    m=2;
    else if((a[8]=='x'&&a[0]!='o')||(a[1]=='x'&&a[3]=='x'))
    m=0;
    else
    m=0;
    return m;
    case 6: 
    if (a[4]=='x'&&a[3]!='o')//||(a[3]!='x'&&a[3]!='o'))
    m=3;
    else if(a[3]=='x'&&a[4]!='o')
    m=4;
    else if((a[2]=='x'&&a[8]!='o')||(a[8]!='x'&&a[8]!='o'))
    m=8;
     else if(a[8]=='x'&&a[2]!='o')
    m=2;
    else 
    m=2;
    
    return m;
    case 7: 
    if (a[2]=='x'&&a[4]!='o')
    m=4;
    else if(a[0]=='x'&&a[3]!='o')
    m=3;
    else if(a[8]=='x'&&a[7]!='o')
    m=7;
    else if(a[3]=='x'&&a[0]!='o')
    m=0;
    else if(a[4]=='x'&&a[2]!='o')//||(a[2]!='x'&&a[2]!='o'))
    m=2; 
    else if(a[7]=='x'&&a[8]!='o')//||(a[2]=='x'&&a[8]!='o'))
    m=8;
    else if (a[4]=='o'&&a[2]=='x')
    m=1;
    else if (a[8]!='o')
    m=4;
    else if (a[0]!='o')
    m=0;
    return m;
    case 8: 
    if ((a[4]=='x'&&a[1]!='o')||(a[1]!='x'&&a[1]!='o'))
    m=1;
    else if(a[1]=='x'&&a[4]!='o')
    m=4;
    else if((a[6]=='x'&&a[8]!='o')||(a[8]!='x'&&a[8]!='o'))
    m=8;
     else if(a[8]=='x'&&a[6]!='o')
    m=6;
    else 
    m=6;
    return m;
     case 9: 
    if (a[2]=='x'&&a[5]!='o')
    m=5;
    else if(a[5]=='x'&&a[2]!='o')//||(a[2]!='x'&&a[2]!='o'))
    m=2;
     else if(a[6]=='x'&&a[7]!='o')
    m=7;
    else if(a[7]=='x'&&a[6]!='o')//||(a[6]!='x'&&a[6]!='o'))
    m=6;
    else if(a[4]=='x'&&a[0]!='o')
    m=0;
    else if(a[0]=='x'&&a[4]!='o')
    m=4;
    else if(a[8]=='x'&&a[4]=='x'&&a[2]!='o')
    m=2;
    else if(a[4]==' ')
    m=4;
    else
    m=7;
    return m;
    }
    }
    }
    int big(char a[10])
    {
    int z;
    if ((a[0]=='o'&&a[1]=='o')||(a[5]=='o'&&a[8]=='o')||(a[4]=='o'&&a[6]=='o')&&(a[2]==' '))
     z=2;
    else if((a[2]=='o'&&a[1]=='o')||(a[3]=='o'&&a[6]=='o')||(a[4]=='o'&&a[8]=='o')&&(a[0]==' '))
    z=0;
    else if((a[0]=='o'&&a[2]=='o')||(a[4]=='o'&&a[7]=='o')&&(a[1]==' '))
    z=1;
    else if((a[3]=='o'&&a[4]=='o')||(a[2]=='o'&&a[8]=='o')&&(a[5]==' '))
    z=5;
    else if((a[3]=='o'&&a[5]=='o')||(a[1]=='o'&&a[7]=='o')&&(a[4]==' '))
    z=4;
    else if((a[4]=='o'&&a[5]=='o')||(a[0]=='o'&&a[6]=='o')&&(a[3]==' '))
    z=3;
    else if((a[7]=='o'&&a[8]=='o')||(a[0]=='o'&&a[3]=='o')||(a[4]=='o'&&a[2]=='o')&&(a[6]==' '))
    z=6;
    else if((a[7]=='o'&&a[6]=='o')||(a[2]=='o'&&a[5]=='o')||(a[4]=='o'&&a[0]=='o')&&(a[8]==' '))
    z=8;
    else if((a[6]=='o'&&a[8]=='o')||(a[4]=='o'&&a[1]=='o')&&(a[7]==' '))
    z=7;
    else
    z=10;
    return z;
    }
