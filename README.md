//# Muhafiz_oyunu
//c dili kullanılarak yazılan oyun kodu

#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <conio.h>
#include<locale.h>


//not: Avcı=5  Asker=2  Mücevher=3
int main() {
	setlocale(LC_ALL,"turkish");
	int i,j,matris[10][10];
	system("COLOR D");
	srand(time(0));
	for(i=0;i<10;i++)
	{
		for(j=0;j<10;j++)
		{
			if(i==2 && j==4)
			{
				matris[i][j]=5;
		    }
		else
			matris[i][j]=0;
        }
    }
    int x,m,n,a,b;
    int dizia[5];
    int dizib[5];
    for(x=0;x<5;x++)
    {
    	a=rand()%10 ;
     	b=rand()%10 ;
	
     if(matris[a][b]!=5 && matris[a][b]!=3)
     {
     dizia[x]=a;
     dizib[x]=b;
     matris[a][b]=3;
	 }
	 else
	 {
	 	x--;
	 }
   }
   int y;
   int dizim[5];
   int dizin[5];
   for(y=0;y<5;)
  
    {
	
   	m=rand()%10 ;
   	n=rand()%10 ;
   	if(matris[m][n]!=3 && matris[m][n]!=5)
   	{ 
    if(m==dizia[y]-1 && n==dizib[y]-1)
   	{
   		dizim[y]=m;
   		dizin[y]=n;
		matris[m][n]=2;	
		y++;
	}
	else if(m==dizia[y]-1 && n==dizib[y])
   	{
      	dizim[y]=m;
   		dizin[y]=n;	
   		matris[m][n]=2;
   		y++;
	}
	else if(m==dizia[y]-1 && n==dizib[y]+1)
   	{
   		dizim[y]=m;
   		dizin[y]=n;
		matris[m][n]=2;
		y++;
	}
	else if(m==dizia[y] && n==dizib[y]-1)
   	{
   		dizim[y]=m;
   		dizin[y]=n;	
   		matris[m][n]=2;
   		y++;
	}
	else if(m==dizia[y] && n==dizib[y]+1)
   	{
   		dizim[y]=m;
   		dizin[y]=n;
		matris[m][n]=2;
	  	y++;
	}
	else if(m==dizia[y]+1 && n==dizib[y]-1)
   	{
   		dizim[y]=m;
   		dizin[y]=n;	
   		matris[m][n]=2;
   	    y++;
	}
	else if(m==dizia[y]+1 && n==dizib[y])
   	{
   		dizim[y]=m;
   		dizin[y]=n;	
   		matris[m][n]=2;
   	    y++;
	}
	else if(m==dizia[y]+1 && n==dizib[y]+1)
   	{
   		dizim[y]=m;
   		dizin[y]=n;
		matris[m][n]=2;	
	    y++;
	}
    }
    }
    int can=3,e=2,d=4;
    int satira=2,sutuna=4;
    int p;
    etiket: 
    printf(" Avcı=5\n");
    
   /*int g,h;
   for(g=0;g<10;g++)
   {
   	for(h=0;h<10;h++)
   	{
   		if(matris[g][h]==3 || matris[g][h]==2)
   		{
   			printf(" 0   ",matris[g][h]);
		}
		else 
		{
			printf(" %d   ",matris[g][h]);
		}
	}
   	printf("\n\n");
   	
   }
    */

	for(i=0;i<10;i++)
	{
		for(j=0;j<10;j++)
		{
			printf(" %d   ",matris[i][j]);
	    }
		printf("\n\n");
	}
	   for(p=0;p<1;p++)
	{
	   if(matris[dizia[0]][dizib[0]]==0 && matris[dizia[1]][dizib[1]]==0 && matris[dizia[2]][dizib[2]]==0 && matris[dizia[3]][dizib[3]]==0 && matris[dizia[4]][dizib[4]]==0 )
        {
		printf("\nTEBRİKLER KAZANDINIZ :)\n");
		break;
        }
   }
	
    int m11,m12,m21,m22,m31,m32,m41,m42,m51,m52;
    m11=satira-dizia[0];
    m12=sutuna-dizib[0];
    m21=satira-dizia[1];
    m22=sutuna-dizib[1];
    m31=satira-dizia[2];
    m32=sutuna-dizib[2];
    m41=satira-dizia[3];
    m42=sutuna-dizib[3];
    m51=satira-dizia[4];
    m52=sutuna-dizib[4];
    if(m11<0)
    	m11=-1*m11;
	if(m12<0)
    	m12=-1*m12;
	if(m21<0)
    	m21=-1*m21;
	if(m22<0)
    	m22=-1*m22;
	if(m31<0)
    	m31=-1*m31;
	if(m32<0)
    	m32=-1*m32;
	if(m41<0)
    	m41=-1*m41;
	if(m42<0)
    	m42=-1*m42;
	if(m51<0)
    	m51=-1*m51;
	if(m52<0)
    	m52=-1*m52;
	int t1,t2,t3,t4,t5;
	t1=m11+m12;
	t2=m21+m22;
	t3=m31+m32;
	t4=m41+m42;
	t5=m51+m52;
	
	
    if(matris[dizia[0]][dizib[0]]==0)
    	printf("1. Mücevher  Çuvalda/");
    else
    	printf("1. Mücevhere Mesafe:%d/ ",t1);
    if(matris[dizia[1]][dizib[1]]==0)
    	printf("2. Mücevher Çuvalda/");
	else
		printf("2. Mücevhere Mesafe:%d/ ",t2);	
	if(matris[dizia[2]][dizib[2]]==0)
    	printf("3. Mücevher Çuvalda/");
	else
		printf("3. Mücevhere Mesafe:%d/ ",t3);	
	if(matris[dizia[3]][dizib[3]]==0)
    	printf("4. Mücevher Çuvalda/");
	else
		printf("4. Mücevhere Mesafe:%d/ ",t4);	
	if(matris[dizia[4]][dizib[4]]==0)
    	printf("5. Mücevher Çuvalda\n");
	else
		printf("5. Mücevhere Mesafe:%d\n",t5);	
	printf("Can Durumu: %d\n",can);

	for(;can>0;)
	{
	char hareket;
	hareket=getch();
   
   switch(hareket)
   {
   	case 'w': 
   	    if(e==0)
   	    continue;
   	    
    	satira=e-1;
    	sutuna=d;
    	if(matris[e][d]!=2)
   	    {
   		matris[e][d]=0;
	    }
    	if(matris[e-1][d]!=2)
    	{
		matris[e-1][d]=5;
	    }
	    if(matris[e-1][d]==2)
    	{
	
			matris[2][4]=5;
			matris[e][d]=0;
		e=2;
		d=4;
		can--;
	
		if(can==2)
		{
			printf("Muhafıza yakalndığınız için başa döndünüz. Kalan canınız 2'dir.");
			sleep(2);
			system("cls");
		}
		else if(can==1)
		{
			printf("Muhafıza yakalandığınız için başa döndünüz. Kalan canınız 1'dir.");
			sleep(2);
			system("cls");
		}
        }
    	e--;
        
	system("cls");
    goto etiket;
    break;
	
	case 's':
		if(e==9)
		continue;
		
		satira=e+1;
	    sutuna=d;
		if(matris[e][d]!=2)
        {
	    matris[e][d]=0;
	    } 
	    if(matris[e+1][d]!=2)
	    {
	   	 matris[e+1][d]=5;
	    }  
	    if(matris[e+1][d]==2)
	    {
	   	can--;
	   	e=2;
	   	d=4;
	   	matris[2][4]=5;
	   	if(can==2)
		{
			printf("Muhafıza yakalndığınız için başa döndünüz. Kalan canınız 2'dir.");
			sleep(2);
			system("cls");
		}
		else if(can==1)
		{
			printf("Muhafıza yakalandığınız için başa döndünüz. Kalan canınız 1'dir.");
			sleep(2);
			system("cls");
		}
	    }
	    e++;
	   
	system("cls");
	goto etiket;
	break;
	
	case 'a':
		if(d==0)
		continue;
		
    	 satira=e;
    	 sutuna=d-1;
    	 if(matris[e][d]!=2)
	    {
	    matris[e][d]=0;
	    } 
	    if(matris[e][d-1]!=2)
	    {
	    matris[e][d-1]=5;
	    }  
	    if(matris[e][d-1]==2)
	    {
	   	can--;
	   	matris[2][4]=5;
	   	if(can==2)
		{
			printf("Muhafıza yakalndığınız için başa döndünüz. Kalan canınız 2'dir.");
			sleep(2);
			system("cls");
		}
		else if(can==1)
		{
			printf("Muhafıza yakalandığınız için başa döndünüz. Kalan canınız 1'dir.");
			sleep(2);
			system("cls");
		}
	    }
	    d--;
	    
	system("cls");
	goto etiket;
	break;  
	
	case 'd':
		if(d==9)
		continue;
		
	    satira=e;
        sutuna=d+1;
	    if(matris[e][d]!=2)
	    {
	    matris[e][d]=0;
	    } 
	    if(matris[e][d+1]!=2)
	    {
	   	matris[e][d+1]=5;
	    }   
	    if(matris[e][d+1]==2)
	    {
	    matris[2][4]=5;	
	    matris[e][d]=0;
	    	
	   	can--;
	   	
	   	
	   	if(can==2)
		{
			printf("Muhafıza yakalndığınız için başa döndünüz. Kalan canınız 2'dir.");
			sleep(2);
			system("cls");
		}
		else if(can==1)
		{
			printf("Muhafıza yakalandığınız için başa döndünüz. Kalan canınız 1'dir.");
			sleep(2);
			system("cls");
		}
	    } 
	    d++;
	   
	system("cls");
	goto etiket;
	break;  
	
	default :printf("yanlış tuşa bastınız");
	break;	
   }
   
   } 

   	if(can==0)
	{
		printf("\nKAYBETTİNİZ:(");
	}

	
	
	return 0;
}
