## UI Types

- Rich UI : Desktop UI , OS Dependent , UI thread can access System resources (FileSystem, Threads,Sockets,registry), Thick Client

  - windows OS : VB, Delphi , WinForms , WPF , MFC
  - IOS : Swift  + XCode
  - Android : Kotlin , JAVA

- Reachable UI : Web Ui (HTML, CSS , JAVASCRIPT , ASP.net, Asp.net MVC , JSP,PHP) 

- Rich Internet Application UI  ; Rich content reachable (Flash,Active-x,Silverlight , Java Fx) , Reachable Content as Rich  (HTML 5.0 + CSS 3.0 , PWA )

- Hybrid UI : Mobile Apps  (Cordova,Ionic )

  

#### UI Rendering - Windows Operating System

---

- Graphic Drivers API
  - Direct - X (Microsoft Game Developers)
    - Vector Graphics (Resolution Independent)
    - Hardware Acceleration (GPU , Graphics Cards (Nvidia G-Force))
    - Advanced Graphic Operation (3D, Animation ,Effects) 
  - GDI 
    - Raster Graphics (Resolution Dependent)
    - Software Acceleration
    - No Support for 3D,Animation.......
- Abstraction over Graphic Drivers API
  - MFC -> GDI
  - VB -> GDI
  - Winform - GDI
  - WPF - Direct-X

### WPF

---

> Managed API for Direct-x
>
> - PresentationCore.dll
> - PresenatationFramewrok.dll
> - WindowsBase.dll
> - System.XAML.dll



### WPF Authoring

---

- Code Only (from Scratch)
- Code with Markup
- Code with Compiled Markup

### Rich UI Composition

----

> WPF Controls can render Rich UI Composition : Text + Media(Audio,Video,Bitmaps) + Graphics (2D,3D ,Shapes)
>
> "ContentControl"  : Base class supports RichUiComposition



### Layout Controls

---

> Arrange UIControls
>
> Built-in Layout Controls
>
> - StackPanel
> - GridPanel
> - Canvas
> - DockPanel
> - WrapPanel



##### XAML

---

Extensible Application Markup Language : XML document used describe wpf UI obejcts



#### WPF Building Blocks

---

1. XAML
2. Markup Extensions
3. Dependency Property System
4. Styles
5. Triggers
6. Databinding
7. Command Pattern
8. Template (Control,Data,Error)
9. Resource Dictionaries
10. MVVM Pattern



#### Markup  Extensions

---

>  Object - returns a value 
>
> Class Derived from Base Class - System.MarkupExtension
>
> XAML :-  {MarkupExtension}
>
> 
>
> ```C#
> public class TestExtension:System.Window.Markup.MarkupExtension{
>     public override object ProvideValue(.....){
>         return "Hello";
>     }
> }
> 
> .xaml
>     
>     <Button Content="{TestExtension}"></Button>
>     // TestExtension obj=new TestExtension();
>     //object value=obj.ProvideValue()
>     // Button.Content=value
>     
> ```
>
> 



## Styles

> Define skin(theme) for control type
>
> Style is a collection Of Setters
>
> Setter -> Property and Value

```xml
		<Button  Content="Button1" Margin="10" x:Name="button1"></Button>
        <Button  Content="Button2" Margin="10" x:Name="button2"></Button>
        <Button  Content="Button3" Margin="10" x:Name="button3"></Button>
        <Button  Content="Button4" Margin="10" x:Name="button4"></Button>
        <Button  Content="Button5" Margin="10" x:Name="button5"></Button>
```



```C#
 Style _buttonStyle = new Style();

            Setter _heightSetter = new Setter();
            _heightSetter.Property = Button.HeightProperty; //Dependency Property
            _heightSetter.Value = 30d;

            Setter _widthSetter = new Setter(Button.WidthProperty, 100d);
            Setter _fontSizeSetter = new Setter(Button.FontSizeProperty, 12d);
            Setter _foreGroundSetter = new Setter(Button.ForegroundProperty, Brushes.Blue);

            _buttonStyle.Setters.Add(_heightSetter);
            _buttonStyle.Setters.Add(_widthSetter);
            _buttonStyle.Setters.Add(_fontSizeSetter);
            _buttonStyle.Setters.Add(_foreGroundSetter);
            _buttonStyle.Setters.Add(_heightSetter);

            this.button1.Style = _buttonStyle;
            this.button2.Style = _buttonStyle;
            this.button3.Style = _buttonStyle;
            this.button4.Style = _buttonStyle;
            this.button5.Style = _buttonStyle;
```

