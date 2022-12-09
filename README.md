# ceminar007
// Задача 47. Задайте двумерный массив размером m×n, 
// заполненный случайными вещественными числами.

Console.Clear();
Console.WriteLine("Введите m");
int m = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("Введите n");
int n = Convert.ToInt32(Console.ReadLine());
double[,] numbers = new double[m, n];
FillArrayRandomNumbers(numbers);
PrintArray(numbers);

void FillArrayRandomNumbers(double[,] array)
{
    Random random = new Random();
    for(int i = 0; i < array.GetLength(0); i++)
    {
        for(int z = 0; z < array.GetLength(1); z++)
        {
            array[i,z] = random.Next(-100, 100);
        }
    }
}

void PrintArray(double[,] array)
{
    for(int i = 0; i < array.GetLength(0); i++)
    {
        for(int z = 0; z < array.GetLength(1); z++)
        {
            Console.Write($"{array[i, z]} ");
        }
        Console.WriteLine();
    }
}

// Задача 50. Напишите программу, которая на вход принимает позиции элемента в двумерном массиве, 
// и возвращает значение этого элемента или же указание, что такого элемента нет.

Console.Clear();
int[,] numbers = new int[8,5];
FillArrayRandomNumbers(numbers);
PrintArray(numbers);

void FillArrayRandomNumbers(int[,] array)
{
    Random random = new Random();
    for(int i = 0; i < 8; i++)
    {
        for(int j = 0; j < 5; j++)
        {
            array[i,j] = random.Next(-100, 100);
        }
    }
}

void PrintArray(int[,] array)
{
    for(int i = 0; i < 8; i++)
    {
        for(int j = 0; j < 5; j++)
        {
            Console.Write($"{array[i, j]} ");
        }
        Console.WriteLine();
    }
}

Console.WriteLine("Введите индекс строки");
int a = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("Введите индекс столбца");
int b = Convert.ToInt32(Console.ReadLine());
FindNumberByIndex(a, b);
void FindNumberByIndex(int a, int b)
{
    if(a > 8 || b > 5)
    {
        Console.WriteLine("Такого числа нет!");
    }
    else
    {
        object c = numbers.GetValue(a, b);
        Console.Write("Число с заданными индексами = ");
        Console.Write(c);
    }
}

// Задача 52. Задайте двумерный массив из целых чисел. 
// Найдите среднее арифметическое элементов в каждом столбце.

Console.Clear();
Console.WriteLine("Введите колличество строк");
int m = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("Введите колличество столбцов");
int n = Convert.ToInt32(Console.ReadLine());
int[,] numbers = new int[m, n];
FillArrayRandomNumbers(numbers);
PrintArray(numbers);
ArithmeticMeanColumn(numbers);

void FillArrayRandomNumbers(int[,] array)
{
    Random random = new Random();
    for(int i = 0; i < array.GetLength(0); i++)
    {
        for(int z = 0; z < array.GetLength(1); z++)
        {
            array[i,z] = random.Next(1, 20);
        }
    }
}

void PrintArray(int[,] array)
{
    for(int i = 0; i < array.GetLength(0); i++)
    {
        for(int z = 0; z < array.GetLength(1); z++)
        {
            Console.Write($"{array[i, z]} ");
        }
        Console.WriteLine();
    }
}

void ArithmeticMeanColumn(int[,] array)
{
    for(int z = 0; z < array.GetLength(1); z++)
    {
        double sum = 0;
        for(int i = 0; i < array.GetLength(0); i++)
        {
            sum += array[i,z];
        }
        double arithmeticMean = sum / array.GetLength(0);
        Console.Write($"{arithmeticMean} ");
    }
}
