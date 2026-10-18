# Конкатенація рядків

Конкатенація — це об’єднання двох або більше рядків. У C# для цього використовують оператор `+`.

---

## Базова конкатенація

```csharp
string greeting = "Hello" + " " + "World";
// Результат: "Hello World"
```

Рядки можна об’єднувати зі значеннями, які зберігаються у змінних.

```csharp
string firstName = "John";
string lastName = "Doe";
string fullName = firstName + " " + lastName;
// Результат: "John Doe"
```

---

## Конкатенація рядків і чисел

Якщо один з операндів є рядком, число буде перетворено на текст.

```csharp
string name = "John Doe";
int age = 30;

string message = name + " is " + age + " years old.";
// Результат: "John Doe is 30 years old."
```

Порядок операцій має значення:

```csharp
string result1 = "Sum: " + 2 + 3;   // "Sum: 23"
string result2 = "Sum: " + (2 + 3); // "Sum: 5"
```

---

## Приклад форматованого повідомлення

```csharp
string firstName = "John";
string lastName = "Doe";
int age = 30;

string fullName = firstName + " " + lastName;

Console.WriteLine(fullName);
Console.WriteLine("Hello, " + fullName + "!");
Console.WriteLine(fullName + " is " + age + " years old.");
```
