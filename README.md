# Postfix-Evaluation-
Its an application of stack

#include<stdio.h>

#include<string.h>

void push(int);

void evaluate(char);

char postfix[20];

int stack[100];

int top=-1,i;

void main()

{

int l;

printf("\nEnter the Postfix Expression : ");

gets(postfix);

l=strlen(postfix);

for(i=0;i<l;i++)

{

if(postfix[i]>='0' && postfix[i]<='9')

push(i);

if(postfix[i]=='+'||postfix[i]=='-'||postfix[i]=='*'||postfix[i]=='/'||postfix[i]=='^')

evaluate(postfix[i]);

}

printf("Final Result is %d",stack[top]);

}



void push(int x)

{

top++;

stack[top]=(int)(postfix[i]-48);

}



void evaluate(char c)

{

int a,b,result;

a=stack[top];

stack[top]='\0';

top--;

b=stack[top];

stack[top]='\0';

top--;

switch(c)


{

case '+' : result=b+a;

break;

case '-' : result=b-a;

break;

case '*' : result=b*a;
 
 break;

case '/' : result=b/a;

break;

case '^' : result=b^a;

break;

default : printf("Invalid operator");

exit(0);

}

top++;

stack[top]=result;

}
