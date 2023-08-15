# DC Form Flipper

## Overview

DC.FormFlipper is a COM based component that allows you to support Eastern languages. It supports right-to-left alignment and orientation by flipping the form horizontally 180 degrees.

DC.FormFlipper may be used with any developing language that supports COM based applications like Visual Basic, Visual C++, Borland C++, Delphi and others.

EgyFirst has done a lot of work for you. No need to waste time designing your form again to support multi-languages and Eastern language applications. You design one form and we design the other by flipping it for you.

## Features

If you develop multi-language applications or eastern language applications, you must get DC.FormFlipper. 

Only one line needs to be added in your Form\_Load event and we will flip the form with all its controls for you.

Additionally, you can define alignment (Right 2 Left or Left 2 Right).

**Note:** It is recommended to use DC.FormTranslator with DC.FormFlipper.

**Example:**

```vb
Dim FF as DynamicComponents.FormFlipper()

FF.FlipForm(Me, True) ' Flip form, so it is right 2 left orientation
```

The first image shows the original form:

![original form](images/Aspose.Words.19aade32-d662-41fc-838a-bc05cce7c938.002.png)

The second image shows form after flipping it horizontally 180 degrees:

![flipped form](images/Aspose.Words.19aade32-d662-41fc-838a-bc05cce7c938.003.png)

## System Requirements

DC.FormFlipper runs as a COM class for Developing with Visual Basic.NET under Microsoft Windows 98/NT/2000 or Windows XP. 

## Installing DC.FormFlipper

The DC.FormFlipper setup program will automatically register the DC_FormFlipper10.dll file on your system.

There is no need to manually run RegSvr32.exe on your development system.

## Including DC.FormFlipper

To include DC.FormFlipper in your project:

1. From the Project menu select Add Reference.
2. Click Browse button to locate your DC_FormFlipper10.DLL file which by default is located in [c:\windows\system32](file:///c:/windows/system32). Now the specific DLL is included in your references.

## Deploying DC.FormFlipper

The only file that needs to be distributed with DC.FormFlipper COM applications is DC_FormFlipper10.dll.

This file should be copied to the WinSystem directory which by default is C:\Windows\System32.

## How to Use

### FlipForm

We support eastern languages like Arabic, Chinese, and so on. So we support right-to-left alignment and orientation by rotating the form horizontally 180 degrees.

**Syntax:**

```vb
Function FlipForm(ByRef dm_Form As System.Windows.Forms.Form, ByVal Right2Left As Boolean)
```

**Example:**

```vb
FF.FlipForm(Me, True) ' Flip form, so it is right 2 left now
```

![flipped form](images/Aspose.Words.19aade32-d662-41fc-838a-bc05cce7c938.004.png)

**Note:** It is recommended to use DC.FormTranslator with DC.FormFlipper.

## Tutorial 

This tutorial describes most of the features supported by DC.FormFlipper.

You can also refer to the project example which is installed by default into C:\Program Files\Dynamic Components\Form Flipper\Tutorial\.

```vb
Dim FF As New DynamicComponents.FormFlipper()

Dim CN As New ADODB.Connection()  

Dim oCust As New ADODB.Recordset()

Dim oAccess As New Access.Application()

Dim DAO_DBEngine As New DAO.DBEngine()

Private Sub TestForm_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

  ' Establish DSN
  
  oAccess.DBEngine.RegisterDatabase("DCDM_Nwind", "Microsoft Access Driver (*.mdb)", True, "DBQ=" & VB6.GetPath & "\Nwind.mdb")

  CN.Open("DSN=DCDM_NWind")
   
  oCust.Open("Customers", CN, oCust.CursorType.adOpenKeyset, oCust.LockType.adLockOptimistic)

  PopulateDate()

  FF.FlipForm(Me, True) ' Flip form, so it is right 2 left
  
End Sub
```
