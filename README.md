# Lab_10_dz
Домашняя работа к лабораторной работе №10

# Условия задачи
Составьте программу, которая для заданной фигуры (трапеции) предлагает меню выбора одной из операций:
1. рассчитать площадь;
2. вывести определение фигуры;
3. нарисовать фигуру.
Фигура - равнобедренная трапеция

# Блоксхема
<img width="1139" height="3111" alt="image" src="https://github.com/user-attachments/assets/8acbb000-4f7c-41bd-b50d-9ca25f6e6ef3" />

# Реализация программы
```
#define _CRT_SECURE_NO_DEPRECATE
#include <stdio.h>
#include <locale.h>
#include <math.h>

char symbol;
int h, a, opt;
int S(int a, int h);
void draw(int a, int h), desc(int a, int h);

int main()
{
    system("chcp 1251");

    printf("\nВведите символ для рисования: ");
    scanf(" %c", &symbol);

    printf("\nВведите высоту трапеции (h): ");
    scanf("%d", &h);

    printf("\nВведите длину меньшего основания (a): ");
    scanf("%d", &a);

    if (h <= 0 || a <= 0)
    {
        printf("Ошибка: высота и основание должны быть положительными числами!\n");
        return 1;
    }

    printf("\nВыберите операцию:\n1. Расчитать площадь\n2. Вывести определение фигуры\n3. Нарисовать фигуру\n\n");
    scanf("%d", &opt);

    switch (opt)
    {
    case 1:
        printf("\n%d\n", S(a, h));
        break;
    case 2:
        desc(a, h);
        break;
    case 3:
        draw(a, h);
        break;
    default:
        printf("Введена неизвестная операция!\n");
        break;
    }

    return 0;
}

int S(int a, int h)
{
    int res = a * h;
    return res;
}

void draw(int a, int h)
{
    for (int i = 0; i < h; i++)
    {
        int chars = a + 2 * i;
        int spaces = h - i - 1;
        for (int j = 0; j < spaces; j++)
        {
            printf(" ");
        }
        for (int j = 0; j < chars; j++)
        {
            printf("%c", symbol);
        }
        printf("\n");
    }
}

void desc(int a, int h)
{
    printf("Трапеция - геометрическая планеметрическая фигура, у которой две стороны параллельны, а другие две не параллельны. Данная трапеция имеет высоту %d, длина наименьшего основания - %d, наибольшего основания - %d.", h, a, 2 * a);
}
```
<img width="501" height="334" alt="image" src="https://github.com/user-attachments/assets/b712eb36-2e0a-4ba4-8034-3049e090ea33" />

<img width="1464" height="348" alt="image" src="https://github.com/user-attachments/assets/c606a3cf-f14b-4bbd-babb-a675b3bd53c0" />

<img width="507" height="540" alt="image" src="https://github.com/user-attachments/assets/e62eb917-7fe9-4c95-9137-85ab142cb47b" />


