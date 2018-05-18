#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<time.h>
#include<math.h>
int x,i,j,p,k,l,m,n,q,a,b,y,z,c;
char fuhao [4]={0};
int shuzi [5]={0};
int paixu [5]={0};
char tump [4]={0};
void panduan(int y)//判断用户输入答案是否正确
{
	if(y==z)
		printf("正确！你真棒！\n");
	else
		printf("错误了,下次加油哟~\n正确为：%d\n",y);
}
int fufuhao(int x)//随机数转换为加减乘除
{
		if (x==0)
		return 43;
	else if(x==1)
		return 45;
	else if(x==2)
		return 42;
	else 
		return 47;
}
int daan(int shuzi[],char fuhao[])//计算四则运算答案
{
	for(j=3,x=0;x<=j;x++)
	{
		if(fuhao[x]=='*'||fuhao[x]=='/')//一级运算
		{
		 if(fuhao[x]=='*')
			shuzi[x]=shuzi[x]*shuzi[x+1];

		 if(fuhao[x]=='/')
			shuzi[x]=shuzi[x]/shuzi[x+1];
		 p=x;
		for(i=1;i<=j-x;i++,p++)
	        {
				
	        	fuhao[p]=fuhao[p+1];
				shuzi[p+1]=shuzi[p+2];
	        }
		j--;
		x=-1;
		}
	}
	for(x=0;x<=j;x++)//二级运算
	{
		 if(fuhao[x]=='+')
			shuzi[x]=shuzi[x]+shuzi[x+1];

		 if(fuhao[x]=='-')
			shuzi[x]=shuzi[x]-shuzi[x+1];
		p=x;
		for(i=1;i<=j-x;i++,p++)
	        {
	        	fuhao[p]=fuhao[p+1];
				shuzi[p+1]=shuzi[p+2];
	        }
		j--;
		x=-1;
		
	}	
	return shuzi[0];
}
void huanwei(int m,int n)
{
	c=m;
	m=n;
	n=c;
}
void fuzhi(int m,int n)
{
	if(m>n)
		huanwei(m,n);
    shuzi[0]=m+rand()%(n-m+1);           //随机数字赋值
	shuzi[1]=m+rand()%(n-m+1);
	shuzi[2]=m+rand()%(n-m+1);
	shuzi[3]=m+rand()%(n-m+1);
	shuzi[4]=m+rand()%(n-m+1);
	
}
void fuzhi2(int m,int n)
{
	if(m>n)
		huanwei(m,n);
	fuhao[0]=fufuhao(rand()%4);             //符号赋值
	fuhao[1]=fufuhao(rand()%4);
	fuhao[2]=fufuhao(rand()%4);
	fuhao[3]=fufuhao(rand()%4);

	for(q=0;q<4;q++)       
	{
	while((fuhao[q]=='/'&&shuzi[q+1]==0)||((fuhao[q]=='-'||fuhao[q]=='/')&&(shuzi[q]<shuzi[q+1]))||(fuhao[q]=='/'&&shuzi[q]%shuzi[q+1]!=0))
	{
		if(fuhao[q]=='/'&&shuzi[q+1]==0)  //判断被除数是否为0
			do
			{
				shuzi[q+1]=m+rand()%(n-m+1);
			}while(shuzi[q+1]==0);
			if((fuhao[q]=='-'||fuhao[q]=='/')&&(shuzi[q]<shuzi[q+1]))//判断是否为分数或负数
			{
				c=shuzi[q+1];
				shuzi[q+1]=shuzi[q];
				shuzi[q]=c;
			}
		if(fuhao[q]=='/'&&shuzi[q]%shuzi[q+1]!=0)//判断是否整除
			do
			{
				shuzi[q]=m+rand()%(n-m+1);
				shuzi[q+1]=m+rand()%(n-m+1);
			}while(shuzi[q]%shuzi[q+1]==0);
	}
	}
	for(i=0;i<5;i++)
		paixu[i]=shuzi[i];
	for(i=0;i<4;i++)
		tump[i]=fuhao[i];
}
void fuzhi3(int m,int n)//判断答案是否为负数
{
	while(daan(paixu,tump)<0)
	{
		fuzhi(m,n);
		fuzhi2(m,n);
	}
}
void shuchu()//输出表达式
{
	 for(x=0;x<4;x++)      
	{		
		printf("%d",shuzi[x]);
		 printf("%c",fuhao[x]);	 
	}
	printf("%d=",shuzi[4]);
}
void yuanze()//四则运算菜单
{
	void one();
	void two();
	void mn();
	printf("请选择相应的操作......");
	scanf("%d",&l); 
		switch(l)
		{
	    case 1: one();break; //一位数
		 case 2: two();break;   //两位数
		 case 3: mn();break;   //[M，N]
			 case 4: k=1;break;
		default: printf("输入数字错误,请重新选择\n");  //解决用户可能的输入错误
		}
}
void one()//0-9四则运算
{
	fuzhi(0,9);
	fuzhi2(0,9);
	fuzhi3(0,9);
	shuchu();
	scanf("%d",&z);
	panduan(daan(shuzi,fuhao));
	yuanze();
}
void two()//0-99四则运算
{
	fuzhi(0,99);
	fuzhi2(0,99);
	fuzhi3(0,99);
	shuchu();
	scanf("%d",&z);
	panduan(daan(shuzi,fuhao));	
	yuanze();
}
void mn()//m-n四则运算
{
	printf("请输入m n的值：");
	scanf("%d%d",&m,&n);
	fuzhi(m,n);
	fuzhi2(m,n);
	fuzhi3(m,n);
	shuchu();
	scanf("%d",&z);
	panduan(daan(shuzi,fuhao));
	yuanze();
}
void operation()
{		 system("cls");
	printf("\t\t-------------------------------------\n");
	    printf("\t\t| \t \3   数字运算游戏\3       |\n");
		printf("\t\t|------------------------------------|\n");
	    printf("\t\t|\t\4 1->一位数四则运算式      |\n");
	    printf("\t\t|\t\4 2->两位数四则运算式      |\n");
		printf("\t\t| \t\4 3->随机产生[M N]之间的数字进行四则运算|\n");
		printf("\t\t| \t\4 4->返回主菜单   \t   |\n");
	    printf("\t\t-------------------------------------\n");
		yuanze();	
}
/**********数字运算函数**********/
void maopao()
{
	for(j=0;j<4;j++)           /*冒泡排序*/
		for(i=0;i<4-j;i++)
			if(shuzi[i]>shuzi[i+1]) 
			{
				p=shuzi[i];
				shuzi[i]=shuzi[i+1];
				shuzi[i+1]=p;
			}
}
void panduan2()
{
	if(a==shuzi[0]&&b==shuzi[4])
				printf("正确！你真棒！");
			else
				printf("错误了,下次加油哟~\n正确为：%d %d",shuzi[0],shuzi[4]);
}
void three()//0-9最值
{
	void yuanze2();
	fuzhi(0,9);
	for(i=0;i<=4;i++)
		printf("%d ",shuzi[i]);
	printf("\n请输入其中的最小值和最大值：");
	scanf("%d%d",&a,&b);
	maopao();
			panduan2();
			yuanze2();
}
void four()
{
	void yuanze2();
	printf("请输入m n的值：");
	scanf("%d%d",&m,&n);
		fuzhi(m,n);
	for(i=0;i<=4;i++)
		printf("%d ",shuzi[i]);
	printf("\n请输入其中的最小值和最大值：");
	scanf("%d%d",&a,&b);
	maopao();
			panduan2();
			yuanze2();
}
void yuanze2()
{
	printf("\n请选择相应的操作......");
	scanf("%d",&l); 
		switch(l)
		{
	    case 1: three();break; //一位数最值
	    case 2: four();break;   //[M，N]最值
	    case 3: k=1;break;
		default: printf("输入数字错误,请重新选择\n");  //解决用户可能的输入错误
		}
}
void maxmin()
{		 system("cls");
		printf("\t\t------------------------------------\n");
	    printf("\t\t| \t \3  数字最值游戏\3     |\n");
		printf("\t\t|-----------------------------------|\n");
	    printf("\t\t|\t\4 1->五个一位数求最值      |\n");
	    printf("\t\t|\t\4 2->[M N]之间求最值      |\n");
		printf("\t\t| \t\4 3->返回主菜单   \t   |\n");
	    printf("\t\t------------------------------------\n");
		yuanze2();
		
}
/**********比较大小函数**********/
void yuanze3()
{
	void five();
	void six();
	printf("\n请选择相应的操作......");
	scanf("%d",&l); 
		switch(l)
		{
	    case 1: five();break; //一位数排序
	    case 2: six();break;   //[M，N]排序
	    case 3: k=1;break;
		default: printf("输入数字错误,请重新选择\n");  //解决用户可能的输入错误
		}
}
void chongfu(int m,int n)
{
	 for(i=0;i<5;i++)     /*检查随机数组是否重复*/
	{
		for(j=0;j<i;j++)
		{
			while(shuzi[j]==shuzi[i])
				shuzi[i]=m+rand()%(n-m+1);
		}
		for(j=i+1;j<=4-i;j++)
			while(shuzi[i]==shuzi[j])
			shuzi[j]=m+rand()%(n-m+1);
	}
}
void panduan3()
{
	for(i=0,j=0,p=0;i<=4;i++,j++)/*检查是否相等*/
				{if(shuzi[i]!=paixu[j])
				p++;}
			if(p!=0)
			{
				printf("错误了,下次加油哟~\n正确为：");
			for(i=0;i<=4;i++)
					printf("%d ",shuzi[i]);
			}
			else
					printf("正确！你真棒！");
}
void five()
{
	fuzhi(0,9);
    chongfu(0,9);
	for(i=0;i<5;i++)       /*输出随机数组*/
		printf("%d  ",shuzi[i]);
	printf("\n请输入从小到大的排序结果：\n");
	for(i=0;i<=4;i++)       /*输入用户排序数组*/
		scanf("%d",&paixu[i]);
	maopao();
		panduan3();	
			yuanze3();
}
void six()
{
	printf("请输入m n的值：");
	scanf("%d%d",&m,&n);
	fuzhi(m,n);
    chongfu(m,n);
	for(i=0;i<5;i++)       /*输出随机数组*/
		printf("%d  ",shuzi[i]);
	printf("\n请输入从小到大的排序结果：\n");
	for(i=0;i<=4;i++)       /*输入用户排序数组*/
		scanf("%d",&paixu[i]);
	maopao();
			panduan3();
			yuanze3();
}
void sort()
{	 system("cls");
		printf("\t\t------------------------------------\n");
	    printf("\t\t| \t \3  数字排序游戏\3     |\n");
		printf("\t\t|-----------------------------------|\n");
	    printf("\t\t|\t\4 1->五个一位数排序      |\n");
	    printf("\t\t|\t\4 2->[M N]之间排序      |\n");
		printf("\t\t| \t\4 3->返回主菜单   \t   |\n");
	    printf("\t\t------------------------------------\n");
		yuanze3();
		
}
/**********数字排序函数**********/
int main()
{   
	
	srand(time(NULL));
     k=1;
	while(k)
	{   system("cls");
	    /**********主菜单**********/
		printf("\t\t------------------------------------\n");
	    printf("\t\t| \t \3   小朋友益智游戏\3     |\n");
		printf("\t\t|----------------------------------|\n");
	    printf("\t\t| \t \4 1->数字运算游戏   \t   |\n");
	    printf("\t\t| \t \4 2->比较大小游戏   \t   |\n");
		printf("\t\t| \t \4 3->数字排序游戏   \t   |\n");
		printf("\t\t| \t \4 4->退出    程序   \t   |\n");
	    printf("\t\t------------------------------------\n");
		printf("请选择相应的操作......");
		scanf("%d",&l); 
		switch(l)
		{
	    case 1: operation();break; //数字运算函数
		 case 2: maxmin();break;   //比较大小函数
		 case 3: sort();break;   //数字排序函数
	    case 4: k=0;break;        //退出程序 
		default: printf("输入数字错误,请重新选择\n");  //解决用户可能的输入错误
		}
	}
		return 0;
}





