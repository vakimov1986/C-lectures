У C# **тип** визначає:

* які значення може зберігати змінна;
* які операції над ними можливі;
* скільки пам’яті потрібно;
* де зберігаються дані (у стеку чи в керованій кучі).

---

### 📊 UML-структура типів у C#:

```mermaid
flowchart TB
    linkStyle default stroke-width:1,stroke:black

    A["System.Object"] --> B["Типи в C#"]
    B --> C
    B --> D

    %% Value types
    subgraph C ["Типи значень"]
    direction TB
        C1["Цілі: sbyte, byte, short, ushort, int, uint, long, ulong<br/>
        Дійсні: float, double<br/>
        Десяткові: decimal<br/>
        bool, char<br/>
        enum<br/>
        struct<br/>
        DateTime, TimeSpan"]
    end

    %% Reference types
    subgraph D ["Посилальні типи"]
    direction TB
        D1["class<br/>
        interface<br/>
        string<br/>
        array (T[])<br/>
        delegate<br/>
        object (базовий тип)"]
    end
```

---

### Опис груп

**Типи значень**

* Зберігають дані безпосередньо у стеку.
* При присвоєнні створюється копія значення.
* Приклади: `int`, `double`, `decimal`, `bool`, `char`, `DateTime`.

**Посилальні типи**

* Зберігають посилання на дані у керованій кучі.
* При присвоєнні копіюється лише посилання, а не сам об’єкт.
* Приклади: `class`, `string`, `array`, `delegate`, `object`.
