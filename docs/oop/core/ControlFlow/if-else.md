# Оператор `if-else`

Конструкція `if-else` обирає один із двох блоків коду. Блок `if` виконується для істинної умови, а блок `else` — для хибної.

```csharp
if (condition)
{
    // Умова істинна
}
else
{
    // Умова хибна
}
```

Завжди виконується лише один із двох блоків.

```csharp
int temperature = 30;

if (temperature > 30)
{
    Console.WriteLine("Спекотно!");
}
else
{
    Console.WriteLine("Не спекотно.");
}
```

**Результат виконання:**

```text {.execution-result}
Не спекотно.
```

## Приклад: парне або непарне число

```csharp
if (number % 2 == 0)
{
    Console.WriteLine("Even");
}
else
{
    Console.WriteLine("Odd");
}
```

Якщо альтернативної дії немає, достатньо використати звичайний `if` без `else`.
