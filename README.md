%{ #include<stdio.h>
    int x;
    int y;
    int sum=0;
%}
range [0-9]*
%%
{range} {return atoi(yytext);}
. {printf("WRONG INPUT");}
%%
int yywrap()
{
    return 1;
}
int main()
{
    printf("Enter any two numbers : ");
    x = yylex();
    y = yylex();
    sum=x+y;
    printf("Sum of two numbers: %d\n",sum);
    return 0;
}

