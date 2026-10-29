# Тип `char`

Тип `char` представляє один символ Unicode. На відміну від `string`, який може містити багато символів, значення `char` завжди містить рівно один символ.

У C# `char` — це **16-бітний тип**, тобто він займає **2 байти** пам’яті та зберігає одну кодову одиницю UTF-16.

---

## Оголошення змінних

Символьні значення записують в одинарних лапках.

```csharp
char letter = 'A';
char digit = '7';
char symbol = '@';
char newline = '\n';
```

---

## Порівняння з `string`

```csharp
char character = 'H';  // один символ в одинарних лапках
string text = "H";     // рядок у подвійних лапках
string empty = "";     // порожній рядок дозволено
// char empty = '';     // помилка: char повинен містити символ
```

---

## Корисні методи

```csharp
char c = 'A';

bool isLetter = char.IsLetter(c); // true
bool isDigit = char.IsDigit(c);   // false
bool isUpper = char.IsUpper(c);   // true
bool isLower = char.IsLower(c);   // false
char lower = char.ToLower(c);     // 'a'
```

---

## Отримання символу з рядка

```csharp
string language = "CSharp";
char first = language[0]; // 'C'
```

Індексація рядка починається з нуля, тому `[0]` повертає перший символ.
