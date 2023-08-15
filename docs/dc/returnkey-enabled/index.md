## **DynamicComponents - ReturnKeyEnable**

Overview
---------

DC.ReturnKeyEnable is a COM based component that enables you to navigate through form controls using the Return key as with the Tab key.

DC.ReturnKeyEnable may be used with any developing language that supports COM based applications like Visual Basic, Visual C++, Borland C++, Delphi and others.

EgyFirst has done a lot of work for you. No need to waste time defining events for every control within your form to handle Return key presses. 

You design your form as usual and we allow you to move through its controls as wanted.

## **Features**

Only one line of code and you can easily move through your form controls without any additional programming. 

**That is all!!**

**Example:**

```
RKE.[EnableReturnKey](#chmtopic8)(Me, True) ' Now you can use Return Key to move through controls instead of Tab Key
```

## **System Requirements** 

DC.ReturnKeyEnable runs as a COM class for developing with Visual Basic.Net under Microsoft Windows 98/NT/2000 or Windows XP.

## **Installing DC.ReturnKeyEnable**

The DC.ReturnKeyEnable setup program will automatically register the DC_ReturnKeyEnable10.dll file on your system.  

There is no need to manually run RegSvr32.exe on your development system. 

## **Including DC.ReturnKeyEnable**

To include DC.ReturnKeyEnable in your project:

1. From Project menu select Add Reference.

2. Click Browse button to locate your DC_ReturnKeyEnable10.DLL file which by default is located in [c:\windows\system32](file:///c:/windows/system32). Now the specific DLL is included in your references.

## **Deploying DC.ReturnKeyEnable Applications**

The only file that needs to be distributed with DC.ReturnKeyEnable COM applications is DC_ReturnKeyEnable10.dll.

This file should be copied to the WinSystem directory which by default is C:\Windows\System32.

## **EnableReturnKey**

Enables you to navigate through controls with the Return key as with the tab key.

**Syntax:** 

```
Function EnableReturnKey(ByVal Mode As Boolean)
```

**Example:**

```
RKE.EnableReturnKey(True) 
```

## Tutorial

This tutorial describes most of the features supported by DC.ReturnKeyEnable.

You can also refer to the project example which is installed by default into C:\Program Files\Dynamic Components\ReturnKeyEnable\Tutorial\.

```
Dim RKE As New DynamicComponents.ReturnKeyEnable()

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

  RKE.EnableReturnKey(Me, True) ' Now you can use Return Key to move through controls instead of Tab Key
  
End Sub
```
