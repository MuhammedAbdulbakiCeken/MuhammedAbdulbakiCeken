#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <math.h>
void tahminKontrolu(int,int,int*,int*,int*,int*);


int main() {
FILE  *belge;
char karakter;
belge=fopen("C:\\Users\\HP\\OneDrive\\Masaüstü\\oyunum.txt","r");

do 
{
	karakter=getc(belge);
	printf("%c ",karakter);
}
while(karakter!=EOF);
fclose(belge); 
	
	

	
	
	int tahmin1,tahmin2,pts1=0,pts2=0,sayi,a=0;
	srand(time(0));
	sayi=(rand()%1000)+1;
	printf("\n rastgele bir sayi olusturuldu \n");
	
	
	while(a!=1)
	{
	
	
	
	
		printf("\n******************************\n");
		printf("birinci yarismacinin tahmini:   ");
		scanf("%d",&tahmin1);
		printf("ikinci yarismacinin tahmini:  ");
		scanf("%d",&tahmin2);
		if(tahmin1<0 || tahmin2<0)
		printf("gecersiz bir sayi tahmini yaptiniz lutfen pozitif bir tahmin ile tekrar deneyiniz");
		else{
			
			tahminKontrolu(tahmin1,tahmin2,&pts1,&pts2,&sayi,&a);
			
		}
		
			
		
	
	}
	printf("\n puanlar\n");
	printf("1. yarismaci:%d \n",pts1); 
	printf("2. yarismaci:%d\n",pts2);
	if(pts1<pts2)
	{
		printf("ikinci oyuncu kazandi:\n");
	}
	else if(pts2<pts1)
	{
		printf("birinci oyuncu kazandi\n");
		
	}
	else if(pts1==pts2)
	{
		printf("yarismacilar berabere kaldi\n");
		
	}
else
{
	printf("boyle bir ihtimal olamaz:)))");
}
	
	
	
	
	
	
	
	
	return 0;
}



void tahminKontrolu(int one,int two,int *pts1,int *pts2,int *sayi,int *a){
	
	
	printf("1. yarismacinin tahmininin sayiya yakinligi:%d.\n",abs(*sayi-one));
	printf("2. yarismacinin tahminin sayiya yakinliği:%d.\n",abs(*sayi-two));
	
	
	
	if(one==*sayi)
	{
		printf("1. yarismaci sayiyi dogru tahmin etti. \n");
		(*pts1)++;
		*a=1;
	}
	else if(two==*sayi)
	{
		printf("2. yarismaci sayiyi dogru tahmin etti.\n");
		(*pts2)++;
		*a=1;
	}
	else if((abs(*sayi-one))<abs(*sayi-two))
	 {
	 	printf("\n 1.yarismacinin tahmini sayiya daha yakin:");
	 	(*pts1)++;
	 }
	 else if ((abs(*sayi-two))<abs(*sayi-one))
	 {
	 	printf("\n 2. yarismacinin tahmini sayiya daha yakin:");
		(*pts2)++;
	 	
	 }
	 else
	 {
	 	printf("\n 1.yarismaci ile 2. yarismacinin  tahminleri ayni");
	 	(*pts1)++;
	 	(*pts2)++;
	 }
	
	
}







