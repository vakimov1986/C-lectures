# Тип `bool`

Тип `bool` представляє логічне значення, яке може бути лише `true` або `false`. Логічні значення використовують для перевірки умов і прийняття рішень у програмі.

---

## Оголошення змінних типу `bool`

```csharp
bool isActive = true;
bool isComplete = false;
bool hasPermission = true;
```

---

## Порівняння повертають `bool`

```csharp
int age = 20;

bool isAdult = age >= 18; // true
bool isTeenager = age < 18; // false
```

---

## Логічні оператори

| Оператор | Назва | Опис |
| -------- | ----- | ---- |
| `&&` | І (AND) | `true`, якщо обидві умови істинні |
| `\|\|` | АБО (OR) | `true`, якщо хоча б одна умова істинна |
| `!` | НЕ (NOT) | змінює значення на протилежне |

```csharp
bool canDrive = hasLicense && isAdult;
bool canEnter = isVip || hasPaid;
bool isClosed = !isOpen;
```

---

## Таблиці істинності

### І (`&&`)

| A | B | A && B |
| - | - | ------ |
| `true` | `true` | `true` |
| `true` | `false` | `false` |
| `false` | `true` | `false` |
| `false` | `false` | `false` |

### АБО (`||`)

| A | B | A \|\| B |
| - | - | --------- |
| `true` | `true` | `true` |
| `true` | `false` | `true` |
| `false` | `true` | `true` |
| `false` | `false` | `false` |

---

## Приклад методу з результатом `bool`

```csharp
public static bool CanGetDrivingLicense(int age)
{
    return age >= 18;
}
```
