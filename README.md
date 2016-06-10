# GZQ007
#define _CRT_SECURE_NO_WARNINGS 1

#ifndef _COMMENT_H__
#define _COMMENT_H__
#include<stdio.h>
#include<stdlib.h>

#define INPUTNAME "input.c"
#define OUTPUTNAME "output.c"

enum STATE //枚举类型
{
	NUL_STATE,
	C_STATE,
	CPP_STATE,
	END_STATE,
};

void Comment(FILE*pfRead, FILE*pfWrite);
void Do_NUL_State(FILE*pfRead, FILE*pfWrite);
void Do_C_State(FILE*pfRead, FILE*pfWrite);
void Do_CPP_State(FILE*pfRead, FILE*pfWrite);

#endif



#define _CRT_SECURE_NO_WARNINGS 1

#ifndef _COMMENT_H__
#define _COMMENT_H__
#include<stdio.h>
#include<stdlib.h>

#define INPUTNAME "input.c"
#define OUTPUTNAME "output.c"

enum STATE //枚举类型
{
	NUL_STATE,
	C_STATE,
	CPP_STATE,
	END_STATE,
};

void Comment(FILE*pfRead, FILE*pfWrite);
void Do_NUL_State(FILE*pfRead, FILE*pfWrite);
void Do_C_State(FILE*pfRead, FILE*pfWrite);
void Do_CPP_State(FILE*pfRead, FILE*pfWrite);

#endif



#define _CRT_SECURE_NO_WARNINGS 1
#include"contact.h"

int main()
{
	FILE*pfRead = NULL;
	FILE*pfWrite = NULL;
	printf("转换开始\n");
	pfRead = fopen(INPUTNAME, "r");
	if (NULL == pfRead)
	{
		perror("EXIT_FAILURE");
		exit(EXIT_FAILURE);
	}
	pfWrite = fopen(OUTPUTNAME, "w");
	if (NULL == pfWrite)
	{
		fclose(pfRead);
		perror("EXIT_FAILURE");
		exit(EXIT_FAILURE);
	}
	Comment(pfRead, pfWrite);
	printf("转换结束");
	system("pause");
	return 0;
}
