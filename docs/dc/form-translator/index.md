# DCForm Translator  

## Overview

DC.FormTranslator is a COM based component that allows you to support multi-language applications, by populating form labels with predefined translations automatically.

DC.FormTranslator may be used with any developing language that supports COM based applications like Visual Basic, Visual C++, Borland C++, Delphi, etc.

EgyFirst has done a lot of work for you. No need to waste time designing your form again to support multi-languages and Eastern language applications. You design one form and we design the other by translating it for you.

## Features

If you develop multi-language applications or eastern language applications, you must get DC.FormTranslator.

Only one line needs to be added in your Form_Load event and we will translate the form with all its labels for you.

**Note:** It is recommended to use DC.FormFlipper with DC.FormTranslator. 

**Example:**

```vb
Dim FT as DynamicComponents.FormTranslator() 

FT.TranslateForm(Me, CN, 2) 'Translate form into French
```

Where CN is your DSN, and parameter 2 is the language id, here it refers to French language.


1) First image shows original form in English:

![original english](images/Aspose.Words.d68589ff-bca5-455c-9b10-b6946f286dbf.002.png)

2) Second image shows form after translating it into French: 

![french translation](images/Aspose.Words.d68589ff-bca5-455c-9b10-b6946f286dbf.003.png)

## System Requirements

DC.FormTranslator runs as a COM class for Developing with Visual Basic.NET under Microsoft Windows 98/NT/2000 or Windows XP.

## Installing DC.FormTranslator

The DC.FormTranslator setup program will automatically register the DC_FormTranslator10.dll file on your system.

There is no need to manually run RegSvr32.exe on your development system.

## Including DC.FormTranslator 

To include DC.FormTranslator in your project:

1. From the Project menu select Add Reference.
2. Click Browse button to locate your DC_FormTranslator10.DLL file which by default is located in [c:\windows\system32](file:///c:/windows/system32). Now the specific DLL is included in your references.


## Deploying DC.FormTranslator Applications 

The only file that needs to be distributed with DC.FormTranslator COM applications is DC_FormTranslator10.dll.

This file should be copied to the WinSystem directory which by default is C:\Windows\System32.

## TranslateForm

We support multi-language applications. You can use the same application with different languages. 

All you need is: 

1. Create a new table, name it "Multilanguage" and put it in your database.
2. Create 4 fields as specified:

| Name | Type | Length | 
|-|-|-|
| Tag | Text | 50 |
| Id | Text | 50 |  
| Language1 | Text | 50 |
| Language2 | Text | 50 |

3. Fill the Tag field with your Form name. 

4. Fill Id field with your Label name.

5. Fill in the Language1 field with your first language translation. 

6. Fill the Language2 field with your second language translation and so on. You can add as many languages as you like, with no limitations!

**Note:** To change form text put form name in both Tag and Id fields.

**Syntax:** 

```vb
Function TranslateForm(ByRef dm_Form As System.Windows.Forms.Form, ByRef dm_DSN As ADODB.Connection, ByVal dm_Language As Byte)
```

**Example:**

```vb
FT.TranslateForm(Me, CN, 2) 'Translate form into French
```

This will populate your form text and all its labels with your translation in field "Language2" in table "Multilanguage" in database referred to by DSN named CN in this example.

Example of French Translation:

![french translation](TranslateForm.gif)

## Tutorial 

This tutorial describes most of the features supported by DC.FormTranslator.

You can also refer to the project example which is installed by default into C:\Program Files\Dynamic Components\Form Translator\Tutorial\.

```vb
Dim FT As New DynamicComponents.FormTranslator()  

Dim CN As New ADODB.Connection()

Dim oOrders As New ADODB.Recordset()

Dim oAccess As New Access.Application()

Dim DAO_DBEngine As New DAO.DBEngine()


Private Sub TestForm_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

  ' Establish DSN

  oAccess.DBEngine.RegisterDatabase("DCDM_Nwind", "Microsoft Access Driver (*.mdb)", True, "DBQ=" & VB6.GetPath & "\Nwind.mdb")

  CN.Open("DSN=DCDM_NWind")
  
  oOrders.Open("Orders", CN, oOrders.CursorType.adOpenKeyset, oOrders.LockType.adLockOptimistic)

  PopulateDate()

  FT.TranslateForm(Me, CN, 2) 'Translate form into French

End Sub
```
