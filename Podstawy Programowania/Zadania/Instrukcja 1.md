
# Instrukcja 1


```c
#include <stdio.h>
#include <stdlib.h>
```

## Zadanie 1

```c
int numbers[3];
for (int i = 0; i < 3; i++) {
	printf("Podaj liczbe %d:", i+1);
	scanf("%d", &numbers[i]);
}

int biggest = numbers[0];
for (int i = 1; i < 3; i++) {
	if (numbers[i] > biggest) {
		biggest = numbers[i];
	}
}
printf("Najwieksza liczba: %d!\n", biggest);
```

## Zadanie 2

```c
char input[3];

printf("Podaj znaki:");
scanf("%c", &input[0]);
scanf(" %c", &input[1]); // spacja usuwa whitespace z przodu
scanf(" %c", &input[2]);


char latest = input[0];
for (int i = 1; i < 3; i++) {
	if (input[i] > latest) {
		latest = input[i];
	}
}
printf("Znak najpozniejszy w alfabecie to %c", latest);
```

## Zadanie 3

Tutaj jest problem:
normalnie w c można zrobić `scanf` unsigned char przy pomocy `%hhu`, jednak implementacja MinGW której używa code::blocks na Windowsie tego nie wspiera i traktuje to jako `%u`, nadpisując poprzednie dane. Dlatego najpierw pobierany jest int, który potem konwertowany jest na unsigned char

```c
int input_a;
int input_b;

unsigned char a;
unsigned char b;

printf("Enter a:\n");
scanf("%d", &input_a);

printf("Enter b:\n");
scanf("%d", &input_b);
a = (unsigned char) input_a;
b = (unsigned char) input_b;

printf("a, b = %x, %x (%d, %d)\n", a, b, a, b);
printf("a & b = %x (%d)\n", a&b, a&b);
printf("a | b = %x (%d)\n", a|b, a|b);
printf("a ^ b = %x (%d)\n", a^b, a^b);
```

## Zadanie 4

```c
int a;
short int b;
double c;
printf("a=%d, b=%hu, c=%lf", a, b, c);
```

## Zadanie 5

```c
int a, b;
printf("Enter a:");
scanf("%d", &a);
printf("Enter b:");
scanf("%d", &b);

printf("%d / %d = %d\n", a, b, a / b);
```


## Zadanie 6

```c

int a, b;
printf("Enter a:");
scanf("%d", &a);
printf("Enter b:");
scanf("%d", &b);

if (a % b == 0) {
	printf("%d\n", a);
}
else {
	printf("%d\n", b);
}
```

## Zadanie 7

```c
int a;
printf("Enter a:");
scanf("%d", &a);

if( a - (2 * (a/2)) ) {
	printf("Liczba jest nieparzysta.\n");
}
else {
	printf("Liczba jest parzysta.\n");
}
```

## Zadanie 8

```c
unsigned char x;
x = x - 1;
printf("%d\n", x);
```

## Zadanie 9

### I prawo De Morgana

Prawo zaprzeczania koniunkcji: _negacja koniunkcji jest równoważna alternatywie negacji_

```c
int a, b;

if (~(~a | ~b) == (a & b)) {
	printf("Przykład działa\n");
}
```

### II prawo De Morgana

Prawo zaprzeczenia alternatywy: _negacja alternatywy jest równoważna koniunkcji negacji_

```c
int a, b;

if (~(~a & ~b) == (a | b)) {
	printf("Przykład działa\n");
}
```