# mgd2023
using System;

class Program
{
    static void Main()
    {
        int N = 5;
        string result = PrintNaturalNumbers(N);
        Console.WriteLine(result);
    }

    static string PrintNaturalNumbers(int n)
    {
        if (n == 0)
        {
            return "";
        }
        else
        {
            return n + ", " + PrintNaturalNumbers(n - 1);
        }
    }
}


/// Задача 66: Задайте значения M и N. Напишите программу, которая найдёт сумму натуральных элементов в промежутке от M до N.
/// M = 1; N = 15 -> 120
/// M = 4; N = 8. -> 30

using System;

class Program
{
    static void Main()
    {
        int M = 1;
        int N = 15;
        int sum = CalculateSum(M, N);
        Console.WriteLine("Сумма натуральных чисел от {0} до {1}: {2}", M, N, sum);
    }

    static int CalculateSum(int m, int n)
    {
        if (m > n)
        {
            // Обмен значениями, чтобы m всегда было меньше или равно n
            int temp = m;
            m = n;
            n = temp;
        }

        if (m == n)
        {
            return m;
        }
        else
        {
            return m + CalculateSum(m + 1, n);
        }
    }
}

/// Задача 68: Напишите программу вычисления функции Аккермана с помощью рекурсии. Даны два неотрицательных числа m и n.
/// m = 2, n = 3 -> A(m,n) = 9
/// m = 3, n = 2 -> A(m,n) = 29

using System;

class Program
{
    static void Main()
    {
        int m1 = 2, n1 = 3;
        int result1 = AckermannFunction(m1, n1);
        Console.WriteLine("A({0}, {1}) = {2}", m1, n1, result1);

        int m2 = 3, n2 = 2;
        int result2 = AckermannFunction(m2, n2);
        Console.WriteLine("A({0}, {1}) = {2}", m2, n2, result2);
    }

    static int AckermannFunction(int m, int n)
    {
        if (m == 0)
        {
            return n + 1;
        }
        else if (m > 0 && n == 0)
        {
            return AckermannFunction(m - 1, 1);
        }
        else
        {
            return AckermannFunction(m - 1, AckermannFunction(m, n - 1));
        }
    }
}
