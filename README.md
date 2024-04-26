# Итоговая контрольная 
## Условие задачи

Задача алгоритмически не самая сложная, однако для полноценного выполнения проверочной работы необходимо:

1. Создать репозиторий на GitHub
2. Нарисовать блок-схему алгоритма (можно обойтись блок-схемой основной содержательной части, если вы выделяете её в отдельный метод)
3. Снабдить репозиторий оформленным текстовым описанием решения (файл README.md)
4. Написать программу, решающую поставленную задачу
5. Использовать контроль версий в работе над этим небольшим проектом (не должно быть так, что всё залито одним коммитом, как минимум этапы 2, 3, и 4 должны быть расположены в разных коммитах)

Задача: 
Написать программу, которая из имеющегося массива строк формирует новый массив из строк, длина которых меньше, либо равна 3 символам. Первоначальный массив можно ввести с клавиатуры, либо задать на старте выполнения алгоритма. При решении не рекомендуется пользоваться коллекциями, лучше обойтись исключительно массивами.

Примеры:
```
[“Hello”, “2”, “world”, “:-)”] → [“2”, “:-)”]
[“1234”, “1567”, “-2”, “computer science”] → [“-2”]
[“Russia”, “Denmark”, “Kazan”] → []
```

## Решение
1. Вы находитесь в созданном репозитории Final_test.
2. Блок-схема алгоритма:

>  P.S. Для удобства проверки разных массивов в программе, я использовал `отдельные методы`, функции ввода/вывода в консоль.   
Они не указаны в блок-схеме, также я указал только метод `FilterStrings`.

<img width="369" alt="Screenshot 2024-04-26 at 11 54 06" src="https://github.com/imalikov13943/Final_test/assets/102352450/86b2fde6-a384-4cfe-9168-f986c46b7b30">

Код программы:

```
using System;
using System.Collections.Generic;

class Program
{
    static List<string> FilterStrings(List<string> input)
    {
        List<string> result = new List<string>();
        foreach (string str in input)
        {
            if (str.Length <= 3)
            {
                result.Add(str);
            }
        }
        return result;
    }

    static void PrintArray(string[] array)
    {
        Console.Write("[");
        for (int i = 0; i < array.Length; i++)
        {
            Console.Write($"“{array[i]}”");
            if (i < array.Length - 1)
            {
                Console.Write(", ");
            }
        }
        Console.Write("]");
        Console.WriteLine();
    }

    static void Main()
    {

        List<string> input = new List<string> { "Russia", "Denmark", "Kazan" };
        List<string> result = FilterStrings(input);

        PrintArray(result.ToArray());
    }
}
```