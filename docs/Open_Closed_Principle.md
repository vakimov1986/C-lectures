# Принцип відкритості/закритості (Open/Closed Principle)

Принцип відкритості/закритості можна сформулювати так:  
**Сутності програми мають бути відкриті для розширення, але закриті для зміни.**

Суть цього принципу полягає в тому, що система має бути побудована таким чином, що всі її наступні зміни мають бути реалізовані за допомогою додавання нового коду, а не зміни вже наявного.

## Приклад 1: Клас Cook

Розглянемо найпростіший приклад — клас кухаря:

```csharp
class Cook
{
    public string Name { get; set; }
    public Cook(string name)
    {
        this.Name = name;
    }

    public void MakeDinner()
    {
        Console.WriteLine("Чистимо картоплю");
        Console.WriteLine("Ставимо почищену картоплю на вогонь");
        Console.WriteLine("Зливаємо залишки води, розминаємо варену картоплю в пюре");
        Console.WriteLine("Посипаємо пюре спеціями та зеленню");
        Console.WriteLine("Картопляне пюре готове");
    }
}
```

Використання:

```csharp
Cook bob = new Cook("Bob");
bob.MakeDinner();
```

Однак одного вміння готувати картопляне пюре для кухаря замало. Ми хочемо, щоб він міг готувати різні страви, не змінюючи сам клас `Cook`. Хотілося б, щоб кухар міг приготувати ще щось. І в цьому разі ми підходимо до необхідності зміни функціоналу класу, а саме методу MakeDinner. Але відповідно до принципу, який ми розглядаємо, класи мають бути відкритими для розширення, але закритими для зміни. Тобто, нам треба зробити клас Cook відритим для розширення, але при цьому не змінювати.

## Приклад 2: Патерн «Стратегія»

Для вирішення цього завдання ми можемо скористатися патерном Стратегія. Насамперед нам треба винести з класу й інкапсулювати всю ту частину, яка представляє поведінку, що змінюється. У нашому випадку це метод MakeDinner. Однак це не завжди буває просто зробити. Можливо, у класі багато методів, але на початковому етапі складно визначити, які з них будуть змінювати свою поведінку і як змінювати. У цьому випадку, звісно, треба аналізувати можливі способи зміни і вже на підставі аналізу робити висновки. Тобто, все, що подається зміні, виноситься з класу та інкапсулюється зовні - у зовнішніх сутностях.
Отже, змінимо клас Cook таким чином:

```csharp
class Cook
{
    public string Name { get; set; }

    public Cook(string name)
    {
        this.Name = name;
    }

    public void MakeDinner(IMeal meal)
    {
        meal.Make();
    }
}

interface IMeal
{
    void Make();
}

class PotatoMeal : IMeal
{
    public void Make()
    {
        Console.WriteLine("Чистимо картоплю");
        Console.WriteLine("Ставимо почищену картоплю на вогонь");
        Console.WriteLine("Зливаємо залишки води, розминаємо варену картоплю в пюре");
        Console.WriteLine("Посипаємо пюре спеціями та зеленню");
        Console.WriteLine("Картопляне пюре готове");
    }
}

class SaladMeal : IMeal
{
    public void Make()
    {
        Console.WriteLine("Нарізаємо помідори й огірки");
        Console.WriteLine("Посипаємо зеленню, сіллю і спеціями");
        Console.WriteLine("Поливаємо соняшниковою олією");
        Console.WriteLine("Салат готовий");
    }
}
```

Використання:

```csharp
Cook bob = new Cook("Боб");
bob.MakeDinner(new PotatoMeal());
Console.WriteLine();
bob.MakeDinner(new SaladMeal());
```

**Консольне виведення:**

```
Чистимо картоплю
Ставимо почищену картоплю на вогонь
Зливаємо залишки води, розминаємо варену картоплю в пюре
Посипаємо пюре спеціями та зеленню
Картопляне пюре готове

Нарізаємо помідори й огірки
Посипаємо зеленню, сіллю і спеціями
Поливаємо соняшниковою олією
Салат готовий
```

## Приклад 3: Патерн «Шаблонний метод»

```csharp
abstract class MealBase
{
    public void Make()
    {
        Prepare();
        Cook();
        FinalSteps();
    }
    protected abstract void Prepare();
    protected abstract void Cook();
    protected abstract void FinalSteps();
}

class PotatoMeal : MealBase
{
    protected override void Prepare()
    {
        Console.WriteLine("Чистимо і миємо картоплю");
    }

    protected override void Cook()
    {
        Console.WriteLine("Ставимо почищену картоплю на вогонь");
        Console.WriteLine("Варимо близько 30 хвилин");
        Console.WriteLine("Зливаємо залишки води, розминаємо варену картоплю в пюре");
    }

    protected override void FinalSteps()
    {
        Console.WriteLine("Посипаємо пюре спеціями та зеленню");
        Console.WriteLine("Картопляне пюре готове");
    }
}

class SaladMeal : MealBase
{
    protected override void Prepare()
    {
        Console.WriteLine("Миємо помідори та огірки");
    }

    protected override void Cook()
    {
        Console.WriteLine("Нарізаємо помідори й огірки");
        Console.WriteLine("Посипаємо зеленню, сіллю і спеціями");
    }

    protected override void FinalSteps()
    {
        Console.WriteLine("Поливаємо соняшниковою олією");
        Console.WriteLine("Салат готовий");
    }
}
```

```csharp
class Cook
{
    public string Name { get; set; }

    public Cook(string name)
    {
        this.Name = name;
    }

    public void MakeDinner(MealBase[] menu)
    {
        foreach (MealBase meal in menu)
            meal.Make();
    }
}
```

Використання:

```csharp
MealBase[] menu = new MealBase[] { new PotatoMeal(), new SaladMeal() };

Cook bob = new Cook("Боб");
bob.MakeDinner(menu);
```

**Консольне виведення:**

```
Чистимо і миємо картоплю
Ставимо почищену картоплю на вогонь
Варимо близько 30 хвилин
Зливаємо залишки води, розминаємо варену картоплю в пюре
Посипаємо пюре спеціями та зеленню
Картопляне пюре готове
Миємо помідори та огірки
Нарізаємо помідори й огірки
Посипаємо зеленню, сіллю і спеціями
Поливаємо соняшниковою олією
Салат готовий
```

Таким чином, клас `Cook` закритий для змін, але відкритий для розширення через додавання нових типів страв.