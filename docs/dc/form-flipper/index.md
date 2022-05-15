DC Form Flipper
================


Overview
-----------

DC.FormFlipper is a COM based component that allows you to Support Eastern Language , we support right to left application by changing alignment to right and orientation by flip form horizontally 180  

DC.FormFlipper may be used with any  developing language support COM based application like Visual Basic,Visual C++,Borland C++,Delphi and others ..

EgyFirst has done a lot of work for you. no need to waste time , designing your form again to support multi languages and eastern languages application 
you design one form and we design the other by flipping it for you

Features
---------

If you develop multi language application or eastern language application , you must get DC.FormFlipper
Only one  Line to add in your Form\_Load event  and we will flip the form with all its controls for you  
additionally , you can define alignment (Right 2 Left or Left 2 right)

**Note:**
It is recommended to use DC.FormTranslator with DC.FormFlipper

**Example:**

Dim FF as DynamicComponents.FormFlipper()

FF.[FlipForm](#chmtopic8)(Me, True) ' Flip form ,so it is right 2 left orientation



`First image show orginal form`

![](images/Aspose.Words.19aade32-d662-41fc-838a-bc05cce7c938.002.png)



`Second image show form after flipping it horizontally 180`

![](images/Aspose.Words.19aade32-d662-41fc-838a-bc05cce7c938.003.png)

System Requirements
-------------------

DC.FormFlipper runs as a COM class for Developing with Visual Basic.Net under Microsoft Windows 98/NT/ 2000 or Windows XP. 


Installing DC.FormFlipper
-------------------------

The DC.FormFlipper setup program will automatically register the DC\_FormFlipper10.dll file on your system. 

There is no need to manually run RegSvr32.exe on your development system. 

Including DC.FormFlipper
-------------------------

To include DC.FormFlipper in your project 

1. From Project menu select add reference 
1. Push Browse button to locate your DC\_FormFlipper10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32)  , now the specific DLL included in your references


Deploying DC.FormFlipper
------------------------

The only file needs to be distributed with DC.FormFlipper COM applications is DC\_FormFlipper10.dll

this file should be copied to the WinSystem directory which by default is C:\Windows\System32 


How to Use:
============


**FlipForm**

We support eastern languages Arabic , Chinese and so on 

so we support right to left alignment and orientation , we rotate form horizontally 180

Syntax:
---------

Function FlipForm(ByRef dm\_Form As System.Windows.Forms.Form, ByVal Right2Left As Boolean)

Example:
-----------

FF.FlipForm(Me, True) ' Flip form, so it is right 2 left now


![](images/Aspose.Words.19aade32-d662-41fc-838a-bc05cce7c938.004.png)



**Note:**
It is recommended to use DC.FormTranslator with DC.FormFlipper**

Tutorial
---------

This tutorial describe most of features supported by DC.FormFlipper

also you can refer to the project  example which installed by default into C:\Program Files\Dynamic Components\Form Flipper\Tutorial\


```
Dim FF As New DynamicComponents.FormFlipper()

Dim CN As New ADODB.Connection()

Dim oCust As New ADODB.Recordset()

Dim oAccess As New Access.Application()

Dim DAO\_DBEngine As New DAO.DBEngine()

Private Sub TestForm\_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

'establish DSN

oAccess.DBEngine.RegisterDatabase("DCDM\_Nwind", "Microsoft Access Driver (\*.mdb)", True, "DBQ=" & VB6.GetPath & "\Nwind.mdb")

CN.Open("DSN=DCDM\_NWind")

oCust.Open("Customers", CN, oCust.CursorType.adOpenKeyset, oCust.LockType.adLockOptimistic)

PopulateDate()

FF.FlipForm(Me, True) ' Flip form ,so it is right 2 left 

End Sub
```