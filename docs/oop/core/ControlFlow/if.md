# Оператор `if`

Оператор `if` виконує блок коду лише тоді, коли задана умова має значення `true`.

```csharp
if (condition)
{
    // Виконується, якщо condition == true
}
```

Умова повинна повертати значення типу `bool`.

```csharp
int age = 18;

if (age >= 18)
{
    Console.WriteLine("Ви повнолітні");
}
```

**Результат виконання:**

```text {.execution-result}
Ви повнолітні
```

Якщо умова хибна, блок пропускається, а виконання продовжується після нього.

```csharp
int temperature = 30;

if (temperature > 25)
{
    Console.WriteLine("На вулиці спекотно");
}

Console.WriteLine("Перевірку завершено");
```

**Результат виконання:**

```text {.execution-result}
На вулиці спекотно
Перевірку завершено
```

Для складних умов можна використовувати [оператори порівняння](../BasicTypeOperations/comparison-operators.md) та [логічні оператори](../BasicTypeOperations/logical-operations.md).
