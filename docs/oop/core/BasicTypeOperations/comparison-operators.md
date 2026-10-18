# Оператори порівняння

Оператори порівняння зіставляють два значення та повертають результат типу `bool`: `true` або `false`.

| Оператор | Значення | Приклад |
| -------- | -------- | ------- |
| `==` | дорівнює | `a == b` |
| `!=` | не дорівнює | `a != b` |
| `>` | більше | `a > b` |
| `<` | менше | `a < b` |
| `>=` | більше або дорівнює | `a >= b` |
| `<=` | менше або дорівнює | `a <= b` |

---

## Приклади

```csharp
int a = 10;
int b = 5;

bool isEqual = a == b;          // false
bool isDifferent = a != b;      // true
bool isGreater = a > b;         // true
bool isLess = a < b;            // false
bool isGreaterOrEqual = a >= b; // true
bool isLessOrEqual = a <= b;    // false
```

Не плутайте оператор порівняння `==` з оператором присвоєння `=`.

```csharp
int value = 10;         // присвоєння
bool result = value == 10; // порівняння
```

---

## Перевірка діапазону

Для перевірки належності значення діапазону оператори порівняння поєднують з логічним оператором `&&`.

```csharp
int value = 7;
int min = 1;
int max = 12;

bool isInRange = value >= min && value <= max; // true
```

Щоб перевірити, чи значення перебуває поза діапазоном, використовують оператор `||`.

```csharp
bool isOutOfRange = value < min || value > max;
```
