# CSCS
## Типы данных
```
byte, short, int, long, float, double, decimial, char, string, bool, object, dynamic
Значимые:
int, char, bool, struct
Ссылочные:
class, string, interface, delegate
```
## Типы данных
Все типы наследуют от object, поэтому можно:
```
object obj1 = 42; // Упаковка (boxing) int в object
object obj2 = "Hello"; // string — ссылочный тип
```
## Циклы
```
foreach (int num in numbers) 
{
    Console.WriteLine(num); // 1, 2, 3
}
```
## Массивы
```
int[,] numbers = { {}, {}, {}, {} };
int[] numbers = { 5, 3, 8, 1 };

Array.Sort(numbers);      // { 1, 3, 5, 8 }
Array.Reverse(numbers);   // { 8, 5, 3, 1 }

int index = Array.IndexOf(numbers, 5);
```
## Методы ф
```
void IncrementRef(ref int x)
IncrementRef(ref num);

void Divide(int a, int b, out int quotient, out int remainder)
{
    quotient = a / b;
    remainder = a % b;
}
int q, r;
Divide(10, 3, out q, out r);

int Sum(params int[] numbers)
{
    int sum = 0;
    foreach (int num in numbers)
        sum += num;
    return sum;
}
```
## ООП
```
class Person
{
    // Данные-члены (поля)
    public string Name;
    public int Age;

    // Метод-член
    public void PrintInfo()
    {
        Console.WriteLine($"Name: {Name}, Age: {Age}");
    }
}

class Person
{
    public string Name { get; set; } // Автосвойство
    public int Age { get; init; }    // Можно установить только при инициализации
}
var person = new Person { Name = "Tom", Age = 40 };
// person.Age = 50; // Ошибка, если Age { get; init; }

Наследование
class Animal  // Базовый класс
{
    public void Eat() => Console.WriteLine("Eating...");
}
class Dog : Animal  // Производный класс
{
    public void Bark() => Console.WriteLine("Barking...");
}

Виртуальные и переопределяемые методы
class Animal
{
    public virtual void MakeSound() => Console.WriteLine("Some sound");
}
class Dog : Animal
{
    public override void MakeSound() => Console.WriteLine("Bark!");
}

Абстрактный класс
abstract class Shape
{
    public abstract double GetArea(); // Абстрактный метод
}

Запечатанный класс
sealed class AdminUser : User { } 

// Ошибка: нельзя наследовать от sealed-класса
// class SuperAdmin : AdminUser { }

internal	Доступен в пределах сборки.
protected internal	Доступен в сборке ИЛИ в производных классах.
private protected	Доступен в производных классах ТОЛЬКО в текущей сборке.

Интерфейсы
interface IA { void A(); }
interface IB { void B(); }
interface IC : IA, IB { }
```
