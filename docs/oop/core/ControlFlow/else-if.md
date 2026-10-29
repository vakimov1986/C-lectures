# Ланцюжок `else if`

Ланцюжок `else if` використовують, коли потрібно послідовно перевірити декілька умов. Виконується лише перший блок, умова якого стала істинною.

```csharp
if (condition1)
{
    // Перша умова істинна
}
else if (condition2)
{
    // Друга умова істинна
}
else
{
    // Усі попередні умови хибні
}
```

## Порядок умов

Умови перевіряються зверху вниз, тому порядок має значення. Спочатку слід перевіряти більш строгі умови.

```csharp
int temperature = 85;

if (temperature > 80)
{
    Console.WriteLine("hot");
}
else if (temperature > 60)
{
    Console.WriteLine("warm");
}
else
{
    Console.WriteLine("cold");
}
```

**Результат виконання:**

```text {.execution-result}
hot
```

Якби перевірка `temperature > 60` стояла першою, для значення `85` програма не дійшла б до варіанта `hot`.

## Приклад із діапазонами

```csharp
if (score >= 90)
    grade = 'A';
else if (score >= 80)
    grade = 'B';
else if (score >= 70)
    grade = 'C';
else if (score >= 60)
    grade = 'D';
else
    grade = 'F';
```
