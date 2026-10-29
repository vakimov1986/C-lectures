# Цикл `foreach`

Цикл `foreach` послідовно перебирає елементи колекції. Він сам керує переходом до наступного елемента, тому індекс не потрібен.

```csharp
foreach (type variableName in collection)
{
    // Робота з поточним елементом
}
```

```csharp
string[] names = { "Alice", "Bob", "Charlie" };

foreach (string name in names)
{
    Console.WriteLine(name);
}
```

**Результат виконання:**

```text {.execution-result}
Alice
Bob
Charlie
```

## `foreach` і `for`

```csharp
for (int i = 0; i < names.Length; i++)
{
    Console.WriteLine(names[i]);
}
```

**Результат виконання:**

```text {.execution-result}
Alice
Bob
Charlie
```

`for` надає доступ до індексу. `foreach` зручніший, коли потрібно лише послідовно обробити всі елементи.

Використовуйте `foreach`, коли:

* потрібно обробити кожен елемент;
* індекс елемента не потрібен;
* колекцію не потрібно змінювати під час перебору.
