# Складні властивості

У попередніх темах було розглянуто створення елементів у XAML. Наприклад, ми могли б визначити кнопку наступним чином:

```xml
<Button x:Name="myButton" Width="120" Height="40" Content="Кнопка" HorizontalAlignment="Center" Background="Red" />
```

За допомогою атрибутів ми можемо задати різні властивості кнопки. Властивості Height і Width є простими властивостями. Вони зберігають числове значення. А, наприклад, властивості HorizontalAlignment або Background є більш складними за своєю структурою. Так, якщо ми будемо визначати цю ж кнопку в коді C#, нам потрібно використовувати наступний набір інструкцій:

```csharp
Button myButton = new Button();
myButton.Content = "Кнопка";
myButton.Width = 120;
myButton.Height = 40;
myButton.HorizontalAlignment = HorizontalAlignment.Center;
myButton.Background = new System.Windows.Media.SolidColorBrush(System.Windows.Media.Colors.Red);
```

Щоб вирівняти кнопку по центру, застосовується перерахування HorizontalAlignment, а для встановлення фонового кольору — клас SolidColorBrush. Хоча в коді XAML ми нічого такого не побачили і встановлювали ці властивості набагато простіше за допомогою рядків: Background="Red". Справа в тому, що до XAML-коду застосовуються спеціальні об'єкти — type converter або конвертери типів, які можуть перетворювати значення з XAML у ті типи об'єктів, що використовуються в коді C#.

У той же час ми можемо явніше використовувати ці об'єкти в коді XAML:

```xml
<Button x:Name="MyButton" Width="120" Height="40" Content="Кнопка">
    <Button.HorizontalAlignment>
        <HorizontalAlignment>Center</HorizontalAlignment>
    </Button.HorizontalAlignment>
    <Button.Background>
        <SolidColorBrush Opacity="0.5" Color="Red" />
    </Button.Background>
</Button>
```

Перевагою такого підходу і те, що з об'єктів ми можемо встановити додаткові параметри.

