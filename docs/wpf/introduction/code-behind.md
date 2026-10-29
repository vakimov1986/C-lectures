# Файли окремого коду

При створенні нового проєкту WPF автоматично генеруються два файли: MainWindow.xaml для визначення інтерфейсу користувача та MainWindow.xaml.cs для реалізації логіки програми. Розмітка XAML дозволяє нам створювати інтерфейси, а код C# в MainWindow.xaml.cs — реалізовувати обробники подій та взаємодію з елементами інтерфейсу.

За замовченням у розмітці вікна використовується атрибут x:Class:

```xml
<Window x:Class="XamlApp.MainWindow"
        .......
```

Атрибут x:Class вказує на клас, який представлятиме дане вікно і в який компілюватиметься код в XAML при компіляції. Тобто під час компіляції генеруватиметься клас XamlApp.MainWindow, успадкований від класу System.Windows.Window.

Крім того, у файлі відокремленого коду MainWindow.xaml.cs, який Visual Studio створює автоматично, ми також можемо знайти клас з тим же ім'ям - у даному випадку клас XamlApp.MainWindow. За замовчуванням він має певний код:

```csharp
public partial class MainWindow : Window
{
    public MainWindow()
    {
        InitializeComponent();
    }
}
```

Метод InitializeComponent() клас MainWindow викликає скомпільований раніше код XAML, розбирає його і з нього будує графічний інтерфейс вікна.

## Взаємодія між XAML і C#

Для взаємодії між кодом XAML і C# можна використовувати імена елементів та події. Наприклад, у XAML визначимо два елементи: кнопку та текстове поле:

```xml
<Window x:Class="XamlApp.MainWindow" ... >
    <Grid x:Name="Grid1">
        <TextBox x:Name="TextBox1" Width="150" Height="30" VerticalAlignment="Top" Margin="20" />
        <Button x:Name="Button1" Width="100" Height="30" Content="Кнопка" Click="Button_Click" />
    </Grid>
</Window>
```

Для обробки події натискання на кнопку в MainWindow.xaml.cs додаємо метод:

```csharp
using System.Windows;
namespace XamlApp
{
    public partial class MainWindow : Window
    {
        public MainWindow()
        {
            InitializeComponent();
        }
        private void Button_Click(object sender, RoutedEventArgs e)
        {
            string text = textBox1.Text;
            if (text != "")
            {
                MessageBox.Show(text);
            }
        }
    }
}
```

Тут використовується TextBox1 — елемент, визначений у XAML, для отримання тексту з текстового поля і виведення його в повідомленні.

У підсумку, після натискання на кнопку виводиться текст, введений у текстове поле.

### Важливі моменти

- Імена елементів можуть бути визначені через Name або x:Name, обидва варіанти майже еквівалентні.

- Подія натискання кнопки прив'язується через атрибут Click:

