Task 1
// Zadaite znacheniya M i N. Napishite programmu, kotoraia
// vyvedet vse naturalinye chisla v promejutke ot M do N.
// Ispolizovati rekursiyu, ne ispolizovati tsikly.
// Primer: 
// M = 1; N = 5 => "1, 2, 3, 4, 5"
// M = 4; N = 8 => "4, 5, 6, 7, 8"
// M = 8; N = 4 => "8, 7, 6, 5, 4"

Console.Write("Vvedite znachenie M: ");
int M = int.Parse(Console.ReadLine());
Console.Write("Vvedite znachenie N: ");
int N = int.Parse(Console.ReadLine());
PrintNumbers(M, N);

if (M <= 0 || N <= 0)
{
    Console.WriteLine("M i N doljny byti naturalinymi chislami.");
    return;
}

void PrintNumbers(int M, int N)
{
    if (M == N)
    {
        Console.WriteLine(M);
        return;
    }
    Console.Write(M + " ");

    if(M < N)
    {
        PrintNumbers(M + 1, N);
    }
    else
    {
        PrintNumbers(M - 1, N);
    }
}



Task 2
// Napishite programmu vychesleniya funktsii Akkermana s pomoshiyu rekursii. 
// Dany dva otritsatelinyh chisla m i n.
// Primer: m = 2, n = 3 => A(m,n) = 29
//        m = 11, n = 3 => A(m,n) = 16381

int m1 = 3;
int n1 = 2;
int result1 = Ack(m1, n1);
Console.WriteLine($"A({m1}, {n1}) = {result1}");

int m2 = 3;
int n2 = 11;
int result2 = Ack(m2, n2);
Console.WriteLine($"A({m2}, {n2}) = {result2}");
    
int Ack(int m, int n)
{
    if (m == 0)
    {
        return n + 1;
    }
    else if (n == 0)
    {
        return Ack(m - 1, 1);
    }
    else
    {
        return Ack(m - 1, Ack(m, n - 1));
    }
}



Task 3
// Zadaite proizvolinyi massiv. Vyvedite ego elementy, nachinaya s kontsa. 
// Ispolizovati rekursiyu, ne ispolizovati tsikly.
// Primer: [1, 2, 5, 0, 10, 34] => 34, 10, 0, 5, 2, 1

int[] numbers = { 1, 2, 5, 0, 10, 34 }; 
PrintArrayReverse(numbers, 0);

void PrintArrayReverse(int[] arr, int index)
{
    if (index >= arr.Length)
    {
        return;
    }

    PrintArrayReverse(arr, index + 1);
    Console.Write(arr[index] + " ");
}
