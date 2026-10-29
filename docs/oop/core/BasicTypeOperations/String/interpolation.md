# Інтерполяція рядків

Інтерполяція рядків дає змогу вставляти значення змінних і виразів безпосередньо в текст. Перед рядком ставлять символ `$`, а вирази записують у фігурних дужках `{}`.

---

## Базовий синтаксис

```csharp
string name = "Alice";
int score = 95;

string message = $"Hello, {name}! Your score is {score}.";
```

Для порівняння, те саме повідомлення через конкатенацію:

```csharp
string message = "Hello, " + name + "! Your score is " + score + ".";
```

Інтерполяція зазвичай робить складні повідомлення коротшими та зрозумілішими.

---

## Вставка різних типів

```csharp
int quantity = 3;
double price = 9.99;
decimal total = 29.97m;

Console.WriteLine($"You bought {quantity} items");
Console.WriteLine($"Price per item: ${price}");
Console.WriteLine($"Total: ${total}");
```

**Результат виконання:**

```text {.execution-result}
You bought 3 items
Price per item: $9.99
Total: $29.97
```

---

## Вирази у фігурних дужках

У фігурних дужках можна використовувати C#-вирази.

```csharp
int a = 5;
int b = 3;

Console.WriteLine($"Sum: {a + b}");     // Sum: 8
Console.WriteLine($"Product: {a * b}"); // Product: 15
```

**Результат виконання:**

```text {.execution-result}
Sum: 8
Product: 15
```

---

## Форматування значень

Після виразу можна вказати формат. Наприклад, `F2` виводить число з двома знаками після десяткової крапки.

```csharp
decimal balance = 1000.5m;
Console.WriteLine($"Balance: ${balance:F2}");
// Balance: $1000.50
```

**Результат виконання:**

```text {.execution-result}
Balance: $1000.50
```
