# test
#include <stdio.h>
#include<ctype.h>
#define MAXLINE 100
main()
{	
	int getline(char[],int max);
	double sum, atof(char []);
	
	char line[MAXLINE];
	sum = 0;
	while ((getline(line, MAXLINE)) > 0)
		printf("\t%g\n", sum += atof(line));
	return 0;
}
double atof(char s[])
{
	int i, sign;
	double val, power;
	for (i = 0; isspace(s[i]); i++)
		;
	sign = (s[i] == '-')? -1 : 1;
	if (s[i] == '+' || s[i] == '-')
		i++;
	for (val = 0.0; isdigit(s[i]); i++)
		val = 10.0 * val+ (s[i] - '0');
	if (s[i] == '.') 
		i++;
		for (power = 1.0; isdigit(s[i]); i++) {
			val = 10.0 * val+ (s[i] - '0');
			power *= 10.0;
		}
	
	return sign * val / power;
}
int getline(char s[], int lim)
{
	int c, i;
	i = 0;
	while ((c = getchar()) != EOF && --lim > 0 && c != '\n')
		s[i++] = c;
	if (s[i] = '\n')
		s[i++] = c;
	s[i] = '\0';
	return i;
}
