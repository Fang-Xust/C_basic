# C_basic

猜数字游戏
#define _CRT_SECURE_NO_WARNINGS 1
#include<stdio.h>
#include<stdlib.h>
#include<time.h>

void menu()
{ 
	printf("********************************************\n");
	printf("***********      1、猜数字       ***********\n");
	printf("***********      0、退出游戏     ***********\n");
	printf("********************************************\n");
}

void game()
{ 
	//生成随机数
	//NULL初始化指针
	//int a = 0;
	//int* p = NULL;
	int guess = 0;
	int ret = rand()%100+1;      //返回0-32767的数字,对100取模后返回后两位0-99的数字，加1后返回1-100的数字
	//printf("%d\n",ret);
	//猜数字
	while (1)
	{
		printf("请猜数字：\n");
		scanf("%d",&guess);
		if (guess > ret)
		{
			printf("猜大了。。\n");
		}
		else if (guess < ret)
		{
			printf("猜小了。。\n");
		}
		else
		{
			printf("老铁，你猜对了！\n");
			break;
		}
	}
}
int main()
{
	int input=0;
	srand((unsigned int)time(NULL));           //必须在rand()函数之前调用，并且必须只调用一次
	do
	{
	menu();
	printf("请选择1或者0：\n");
	scanf("%d",&input);
		switch (input)
		{
		case 1:
		{
			printf("猜数字\n");
			game();
			break;
		}
		case 0:
		{
			printf("游戏结束\n");
			break;
		}
		default:
			printf("选择错误，请重新选择：\n");
			break;
		}
	} while (input);
	system("pause");
	return 0;
} 
