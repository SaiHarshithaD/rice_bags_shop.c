# rice_bags_shop.c
#include<stdio.h>
     void checkstokes();
    void sellstock();
    void purchesstock();
    int stock=100;       //intial stock value 
    int countsell=0;
     int countpurches=0;
    int iteamsold=0;
     int iteampurches=0;
    int main()
    {
    static int i,n;
    printf("**WELCOM TO RICE SHOP**\n"); //Greeting massege
    for(i=1;i>0;i++)
    {
    printf("\nChoose Options below :");
    printf("\n1.Check stock");
    printf("\n2.sell stock");
       printf("\n3.purches stock");
    printf("\n4.quit\n");
   scanf("\n%d",&n);
    switch(n)
    {
  
    case 1:  checkstokes();
             continue;
    case 2: sellstock();
            continue;
  
    case 3: purchesstock();
            continue;
    }
    if(n==4)
            {
		// Report of total sells and purches 
            printf("\nReport");
            printf("\nNo of times sales done :%d",countsell);
            printf("\nNo of items sold : %d ",iteamsold);
            printf("\nNo of purches done : %d",countpurches);
            printf("\nNo of items purchesed : %d",iteampurches);
            printf("\n***THANK YOU*");
            break;
            }
    }
   return 0;
    }
    
//check Stock function
 void checkstokes()
  
      {
      printf("No of Rice bags in stockRoom =%d",stock);
      }

//Purches stocks

 void purchesstock()
    {
    int buystock,tempstock;
    printf("\nEnter no of Rice bags to buy :\n ");
    scanf("%d",&buystock);
    tempstock=stock;
    tempstock=tempstock + buystock;
    if(tempstock <= 500)
    {
 	  stock=tempstock;
          countpurches++;
          iteampurches=iteampurches+buystock;
    printf("No of Ricebags in stockroom =%d\n",stock);
    }
    else
          {
          int n;
          printf("sorry we cant buy those many Rice bags\n");
          printf("Options:\n");
          printf("\n1.Do you like to fill the stockroom");
          printf("\n2.Cancle");
          scanf("%d",&n);
          switch(n)
          {
          case 1: countpurches++;
                  tempstock=0;
                  tempstock=500-stock;
                  stock=stock+tempstock;
                  iteampurches=iteampurches+tempstock;
                  printf("\nStock room is full : %d",stock);
                  break;
          case 2:
                   printf("\nSorry Vist again");
          }
          }
    } 

//sell stocks

 void sellstock()
       {
       int buystock;
      printf("\nNo of Rice bags  coustmor wants to buy : ");
        scanf("%d",&buystock);
       if(buystock<=stock)
       {
      stock=stock-buystock;
          countsell++;
          iteamsold=iteamsold+buystock;
      printf("\nNo of Rice bags in stockroom =%d\n",stock);
      }
      else
          {
          int n;
          printf("\nSorry we dont have those many Rice bags");
          printf("\nOptions");
          printf("\n1.Do you like to buy no of Rice bags  we have");
          printf("\n2.cancle");
          scanf("\n%d",&n);
          switch(n)
          {
          case 1:
                  countsell++;
                  iteamsold=iteamsold+stock;
                  stock=0;
                  printf("\nNo of Rice bags remaining =%d",stock);
                  break;
          case 2:
              printf("\nSorry vist again");
          }
          }
      }
