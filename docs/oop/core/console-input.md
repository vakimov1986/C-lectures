# Консольне введення

`Console.ReadLine()` зчитує рядок тексту, який вводить користувач, і повертає його як `string`.
Метод чекає, поки користувач натисне ++enter++, а потім повертає все, що було введено.

## Базове використання

```csharp
Console.Write("Введіть ім'я: ");
string input = Console.ReadLine();
Console.WriteLine("Вітаємо, " + input + "!");
```

## Введення чисел

`Console.ReadLine()` завжди повертає текст, тому для роботи з числом його потрібно перетворити за допомогою `int.Parse()`:

```csharp
Console.Write("Введіть вік: ");
string input = Console.ReadLine();
int age = int.Parse(input);

Console.WriteLine("Ваш вік: " + age);
```
