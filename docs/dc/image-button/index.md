# DC Image Button

## System Requirements

DC.ImageButton runs as a COM class for Developing with Visual Basic.NET under Microsoft Windows 98/NT/2000 or Windows XP.

## Installing DC.ImageButton

The DC.ImageButton setup program will automatically register the DC_ImageButton10.dll file on your system.

There is no need to manually run RegSvr32.exe on your development system. 

## Including DC.ImageButton

To include DC.ImageButton in your project:

1. From the Project menu select Add Reference.
2. Click Browse button to locate your DC_ImageButton10.DLL file which by default is located in [c:\windows\system32](file:///c:/windows/system32). Now the specific DLL is included in your references.

## Deploying DC.ImageButton Applications 

The only file that needs to be distributed with DC.FormFlipper COM applications is DC_FormFlipper10.dll. 

This file should be copied to the WinSystem directory which by default is C:\Windows\System32.

## PrepareImageButtons

This function enables you to assign icon paths for button images. Additionally, you can assign a motion for each button if you set the second parameter to True.

**Syntax:**

```vb
Function PrepareImageButtons(ByVal ImageFullPath As String, ByVal Motion As Boolean)
```

Where:

- ImageFullPath parameter is the path to your button icons. 
- Motion parameter determines if you want to assign a motion to your button icons or not.

**Example:**

```vb
IB.PrepareImageButtons("C:\MyApp\Icons\", True)
```

Where "C:\MyApp\Icons\" is the path to your button icons.
And you determine your buttons to have a motion action.

- Buttons without Motion

![no motion buttons](images/Aspose.Words.0607795d-0f5c-44d4-95ed-bee8978b477f.002.png)

- Buttons with Motion

![motion buttons](images/Aspose.Words.0607795d-0f5c-44d4-95ed-bee8978b477f.003.png)

## AddImageButton

Assigns icons for every button state: when mouse over, mouse down, mouse up.

**Syntax:** 

```vb
Public AddImageButton(ByRef ButtonName As Windows.Forms.Button, ByVal img_MouseLeave As String, ByVal img_MouseEnter As String, ByVal img_MouseDown As String)
```

Where:

- img_MouseLeave parameter is the icon that appears when mouse leaves button. 
- img_MouseEnter parameter is the icon that appears when mouse is over the button.
- img_MouseDown parameter is the icon that appears when mouse is pressed.

**Example:**

```vb
Dim IB As New DynamicComponents.ImageButton()

IB.AddImageButton(Me.FirstButton, "first.ico", "firstover.ico", "firstdown.ico")

IB.AddImageButton(Me.PreviousButton, "previous.ico", "previousover.ico", "previousdown.ico")

IB.AddImageButton(Me.NextButton, "next.ico", "nextover.ico", "nextdown.ico")

IB.AddImageButton(Me.LastButton, "last.ico", "lastover.ico", "lastdown.ico")
```

- Buttons without Motion

![no motion buttons](images/Aspose.Words.0607795d-0f5c-44d4-95ed-bee8978b477f.002.png)

- Buttons with Motion

![motion buttons](images/Aspose.Words.0607795d-0f5c-44d4-95ed-bee8978b477f.003.png)
