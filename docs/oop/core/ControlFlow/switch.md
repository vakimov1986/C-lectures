# Оператор `switch`

Оператор `switch` зручно використовувати, коли одне значення потрібно порівняти з декількома фіксованими варіантами.

```csharp
switch (expression)
{
    case value1:
        // Дії для value1
        break;

    case value2:
        // Дії для value2
        break;

    default:
        // Жоден case не підійшов
        break;
}
```

| Компонент | Призначення |
| --------- | ----------- |
| `case` | визначає значення для порівняння |
| `break` | завершує виконання поточного `case` |
| `default` | обробляє всі невраховані значення |

```csharp
switch (grade)
{
    case 'A':
        result = "Відмінно";
        break;
    case 'B':
        result = "Добре";
        break;
    default:
        result = "Невідомо";
        break;
}
```

## `return` замість `break`

Якщо `switch` розташований у методі, з `case` можна одразу повернути результат.

```csharp
switch (status)
{
    case 1: return "Активний";
    case 2: return "Неактивний";
    default: return "Невідомий";
}
```

`switch` найкраще підходить для набору конкретних значень. Для перевірки діапазонів зазвичай зрозуміліший ланцюжок `else if`.
