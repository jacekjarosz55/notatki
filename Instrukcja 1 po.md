
| Programowanie Obiektowe 1      | Rok akademicki 2023/2024    |
| ------------------------------ | --------------------------- |
| Jacek Jarosz                   | 1ID12B                      |
| Instrukcja nr 1                |                             |
| Liczba zadań zaplanowanych: 11 | Liczba zadań wykonanych: 11 |
| Wtorek 10-12                   | Studia stacjonarne (letni)  |
|                                |                             |
## Zadanie 1

>Zapoznać się z dokumentacją klasy String dostępnej pod adresem 
>http://www.cplusplus.com/reference/string/string/

Zapoznałem się.

## Zadanie 2

>Zapoznać się z dokumentacją klasy Vector dostępnej pod adresem 
>http://www.cplusplus.com/reference/vector/vector/

Zapoznałem się.

## Zadanie 3

>Przygotować funkcje obliczające pole koła, trapezu, trójkąta

```cpp
double area_circle(double radius) {
  return M_PI * radius * radius;
}

double area_trapeze(double a, double b, double h) {
  return (a+b)/2.0 * h;
}

double area_triangle(double a, double h) {
  return (a * h) / 2.0;
}
```

## Zadanie 4

> Przygotować rekurencyjną funkcję liczącą n-ty wyraz Fibonacciego

```cpp
int fibonacci(int i) {
  if (i < 3) {
    return 1;
  }
  return fibonacci(i - 1) + fibonacci(i - 2);
}
```

## Zadanie 5

> Przygotować rekurencyjną funkcję liczącą silnię

```cpp
unsigned int factorial(unsigned int i)
{
  if(i == 1) {
    return 1;
  }
  return i * factorial(i - 1);
}
```

## Zadanie 6

> Umieść wcześniej przygotowane funkcje w osobnych plikach źródłowych

`area_triangle.h`
```cpp
#ifndef AREA_TRIANGLE_H
#define AREA_TRIANGLE_H

double area_triangle(double a, double h);

#endif
```


`area_circle.h`
```cpp
#ifndef AREA_CIRCLE_H
#define AREA_CIRCLE_H

double area_circle(double radius);

#endif
```

`area_trapeze.h`
```cpp
#ifndef AREA_TRAPEZE_H
#define AREA_TRAPEZE_H

double area_trapeze(double a, double b, double h);

#endif
```

`fibonacci.h`
```cpp
#ifndef FIBONACCI_H
#define FIBONACCI_H

int fibonacci(int i);

#endif
```

`factorial.h`
```cpp
#ifndef FACTORIAL_H
#define FACTORIAL_H

unsigned int factorial(unsigned int i);

#endif
```

`fibonacci.cpp`
```cpp
#include "fibonacci.h"

int fibonacci(int i) {
  if (i < 3) {
    return 1;
  }
  return fibonacci(i - 1) + fibonacci(i - 2);
}
```

`factorial.cpp`
```cpp
#include "factorial.h"

unsigned int factorial(unsigned int i)
{
  if(i == 1) {
    return 1;
  }
  return i * factorial(i - 1);
}
```



`area_triangle.cpp`
```cpp
#include "area_triangle.h"

double area_triangle(double a, double h) {
  return (a * h) / 2.0;
}
```

`area_circle.cpp`
```cpp
#include "area_circle.h"

#include <cmath>

double area_circle(double radius) {
  return M_PI * radius * radius;
}
```

`area_trapeze.cpp`
```cpp
#include "area_trapeze.h"

double area_trapeze(double a, double b, double h) {
  return (a+b)/2.0 * h;
}
```


## Zadanie 7

> Przygotować plik Makefile dla programu wykorzystującego pliki z poprzedniego zadania

`Makefile`
```Makefile
program: area_circle.cpp area_triangle.cpp area_trapeze.cpp factorial.cpp fibonacci.cpp
  g++ $^ -o program
clean:
  rm program
```

## Zadanie 8

> Przygotować funkcje liczące średnią dla dwóch, trzech elementów, tablicy elementów, zakresu elementów w tablicy.
> Wykorzystać przeciążanie funkcji.

`avg.cpp`
```cpp
double avg(double a, double b) {
  return (a + b) / 2;
}
double avg(double a, double b, double c) {
  return (a + b + c) / 3;
}

double avg(double vals[], unsigned size) {
  double sum = 0;
  for(unsigned i = 0; i < size; i++) {
    sum += vals[i];
  }
  return sum / size;
}

double avg(double vals[], unsigned start, unsigned end) {
  double sum = 0;
  for(unsigned i = start; i < end; i++) {
    sum += vals[i];
  }
  return sum / (end - start);
}
```

## Zadanie 9

> Przetestować działanie metod klasy string.

`strings.cpp`
```cpp
// ...
 std::string message = "Hello, world!";
  std::cout << "substr(0, 5) = " << message.substr(0, 5) << "\n";
// ...
```
## Zadanie 10

> Przygotować kolekcję typu vector przechowującą obiekty string

`strings.cpp`

```cpp
// ...
  std::vector<std::string> strings;
  strings.push_back("Hello");
  strings.push_back("world");
  strings.push_back("this");
  strings.push_back("is");
  strings.push_back("text");
// ...
```

## Zadanie 11

> Przygotować program wyszukujący podany ciąg we wszystkich łańcuchach w kolekcji vector

`strings.cpp`
```cpp
#include <string>
#include <iostream>
#include <vector>

unsigned long find_string(const std::vector<std::string> &vec,const std::string &value) {
  for (unsigned i = 0; i < vec.size(); i++) {
    if (vec[i].find(value) != std::string::npos) {
      return i;
    }
  }
  return std::string::npos;
}


int main() {
  std::string message = "Hello, world!";
  std::cout << "substr(0, 5) = " << message.substr(0, 5) << "\n";

  std::vector<std::string> strings;

  strings.push_back("Hello");
  strings.push_back("world");
  strings.push_back("this");
  strings.push_back("is");
  strings.push_back("text");

  const std::string value;
  std::cout << "What word to search for? ";
  std::cin >> value;

  unsigned long position = find_string(strings, value);
  if (position == std::string::npos) {
    std::cout << "Couldn't find: " << value << "\n";
  }
  else {
    std::cout << "Found " << value << " at: " << position << "\n";
  }

  return 0;
}
```


