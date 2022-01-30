/*CustomerBill*/
#include <stdio.h>
struct bill {
    int sno;
    char name[25];
    int cost;
};
void display(struct bill b[23])
{
    int i;
    puts("Items list cost per kg:");
    for (i=0;i<23;i++) 
    {printf("%d %s %d\n",b[i].sno,b[i].name,b[i].cost);}
}
void printbill()
{
    int bno,i;
    char date[20],cname[20],phone[12];
    printf("\n\n*****************************Welcome*****************************");
    printf("\n\n Bill no. = ");scanf("%d",&bno);
    printf(" Date = ");scanf("%s",date);
    printf(" Customer name = ");scanf("%s",cname);
    printf(" Phone number = ");scanf("%s",phone);
    printf("\n**************************** Thank you **************************");
}
int main()
{
    struct bill b[23]= { { 1,"apple red",150},{2,"applegreen",220},{3,"applegolden",220},{ 4,"orange",100},
    { 5,"mango\n\t   banganapalli",70},{6,"m.alphonso",170},{7,"m.senthuram",150},{8,"m.neelam",150},
    {9,"bananahill",60},{10,"b.yelaki",50},{11,"b.poovam",70},
    {12,"b.rasthali",100},{13,"b.nendram",110},{14,"banana red",120},{15,"guava",60},{16,"pomegranate",150},
    {17,"grapes gr",50},{18,"sapota",50},
    {19,"plum",200},{20,"strawberry",150},{21,"watermelon",100},
    {22,"seethaphal",100},{23,"mosambi",100},
    };
    display(b);
    int i,n;
    float qty,price,amt=0;
    puts("\nEnter items: !warning!-cannot delete an item which has been added\nif finished,type 0 0\n");
    printf("*******************************BILL*****************************\n");
    printf("item\tqty name\t\t\tcost/kg\t\ttotal\n");
        for(i=0;i<24;i++)
        {
         scanf("%d\t%f",&n,&qty);
        lab:if(n==0){break;}
        if(n==b[i].sno)
            {price=qty*b[i].cost;
            printf("\t    %s\t\t\t%d\t\t%.2f\n",b[i].name,b[i].cost,price);
            amt=amt+price;}
        else{i=n-1;goto lab;}
        }
        printf("\n\tAmount is Rs.%.2f\n\tGST = 14percent\n\tTotal = Rs.%.2f",amt,(0.14*amt)+amt);
    printbill();
    return 0;
}
