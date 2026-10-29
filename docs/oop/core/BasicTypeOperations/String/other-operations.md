# Інші операції з рядками

На цій сторінці зібрані базові операції з рядками, крім конкатенації та інтерполяції.

---

## Довжина рядка

Властивість `Length` повертає кількість символів у рядку.

```csharp
string text = "Programming";
int length = text.Length; // 11
```

---

## Доступ до символу за індексом

Окремий символ можна отримати за індексом у квадратних дужках. Індексація починається з нуля, а результат має тип `char`.

```csharp
string language = "CSharp";

char first = language[0];  // 'C'
char second = language[1]; // 'S'
```

Рядки незмінні, тому замінити символ безпосередньо за індексом не можна.

```csharp
// language[0] = 'B'; // помилка компіляції
```

---

## Зміна регістру

Методи `ToUpper()` і `ToLower()` повертають новий рядок у верхньому або нижньому регістрі.

```csharp
string text = "Hello World";

string upper = text.ToUpper(); // "HELLO WORLD"
string lower = text.ToLower(); // "hello world"
```

---

## Пошук підрядка

Метод `Contains()` перевіряє, чи містить рядок указаний текст, і повертає значення типу `bool`.

```csharp
string text = "I love C#";
bool containsCSharp = text.Contains("C#"); // true
```

---

## Заміна

Метод `Replace()` повертає новий рядок, у якому символ або підрядок замінено іншим значенням.

```csharp
string date = "2026-02-02";
string formattedDate = date.Replace('-', '/');
// "2026/02/02"
```

Початковий рядок при цьому не змінюється.

---

## Escape-послідовності

Escape-послідовності дають змогу записувати в рядку спеціальні символи.

| Послідовність | Опис | Приклад |
| ------------- | ---- | ------- |
| `\n` | новий рядок | `"Line 1\nLine 2"` |
| `\t` | табуляція | `"Hello\tWorld"` |
| `\\` | зворотна коса риска | `"C:\\Users"` |
| `\"` | подвійні лапки | `"He said \"Hi\""` |

```csharp
Console.WriteLine("Line 1\nLine 2");
Console.WriteLine("Hello\tWorld");
Console.WriteLine("C:\\Users\\Documents");
Console.WriteLine("He said \"Hi\"");
```

**Результат виконання:**

```text {.execution-result}
Line 1
Line 2
Hello	World
C:\Users\Documents
He said "Hi"
```
