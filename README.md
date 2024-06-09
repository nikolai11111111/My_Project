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
