# DC Help Authority

## Overview

DC.HelpAuthority is a COM based component that allows you to assign sensitive help for every control within your form or even every column in your grid.

DC.HelpAuthority may be used with any developing language that supports COM based applications like Visual Basic, Visual C++, Borland C++, Delphi and others.

EgyFirst has done a lot of work for you. Now you can develop your application and make it comprehensive by supporting it with your sensitive help.

## Features

DC.HelpAuthority enables you to put the finishing touch on your application by adding sensitive help to every control in your form, any column in your grid. When you press the F12 key this will trigger your sensitive help for the focused control or column.

**Example:**

```vb
Dim HA As New DynamicComponents.HelpAuthority()

HA.PrepareHelp(CN, Me, Me.AxDataGrid1) 
```

![help authority](images/Aspose.Words.ae3310bc-06aa-44b7-b32c-bb0578e2b47e.002.png)

## System Requirements

DC.HelpAuthority runs as a COM class for Developing with Visual Basic.NET under Microsoft Windows 98/NT/2000 or Windows XP.

## Installing DC.HelpAuthority 

The DC.HelpAuthority setup program will automatically register the DC_HelpAuthority10.dll file on your system.

There is no need to manually run RegSvr32.exe on your development system.

## Including DC.HelpAuthority

To include DC.HelpAuthority in your project:

1. From Project menu select Add Reference.
2. Click Browse button to locate your DC_HelpAuthority10.DLL file which by default is located in [c:\windows\system32](file:///c:/windows/system32). Now the specific DLL is included in your references.


## Deploying DC.HelpAuthority Applications

There are two files that need to be distributed with DC.HelpAuthority COM applications:

- DC_HelpAuthority10.dll
- DCHA10_Lang.dll

These files should be copied to the WinSystem directory which by default is C:\Windows\System32.

## PrepareHelp

Prepares the form to know everything about the form and its controls and all binding information.

**Syntax:**

```vb
Function PrepareHelp(ByRef dm_DSN As ADODB.Connection, ByRef dm_Form As System.Windows.Forms.Form, Optional ByRef dm_Grid As AxMSDataGridLib.AxDataGrid = Nothing)
```

- dm_DSN is a reference to your DSN connection.  
- dm_Form is a reference to your form which is passed as the 'Me' keyword.
- Optional dm_Grid (if your form has a grid) is a reference to your grid.


**Example:** 

```vb
Dim HA As New DynamicComponents.HelpAuthority()

HA.PrepareHelp(CN, Me, Me.AxDataGrid1)
```

Where:
- CN is a reference to your DSN connection.  
- Me is a reference to your form which is passed as the 'Me' keyword.
- AxDataGrid1 (if your form has a grid) is a reference to your grid.


![help authority](images/Aspose.Words.ae3310bc-06aa-44b7-b32c-bb0578e2b47e.002.png)

## Sensitive F12 Help

When you press the F12 Key, this triggers sensitive help. This requires:

1. Create a new table, name it "Help" and put it in your database.
2. Create 4 fields as specified:

| Name | Type | Length |
|-|-|-|  
| Tag | Text | 50 |
| Id | Text | 50 |
| Description | Text | 50 |
| Contents | Memo | |

3. Fill Tag field with your [Form Tag](#form-tag). 

4. Fill Id Field with your control name.

5. Fill Id Field with DataGrid name followed with underscore "\_" character, which will be something like:
   ```
   axDatagrid_ProductId
   ```

6. Fill Description field with your control description. 

7. Fill Contents field with your supported help for this control.

**Note:** 

To change your form text put form name in both Tag and Id fields.

![help authority](images/Aspose.Words.ae3310bc-06aa-44b7-b32c-bb0578e2b47e.002.png)


## Configuration Utility

We supply a Configuration Utility which enables you to assign your own language used with DC.HelpAuthority.

![config utility](images/Aspose.Words.ae3310bc-06aa-44b7-b32c-bb0578e2b47e.003.png)

## Tutorial

This tutorial describes most of the features supported by DC.HelpAuthority. 

You can also refer to the project example which is installed by default into C:\Program Files\Dynamic Components\Help Authority\Tutorial\.

```vb
Dim HA As New DynamicComponents.HelpAuthority()

Dim CN As New ADODB.Connection()

Dim oOrders As New ADODB.Recordset()  

Dim oOrderDetails As New ADODB.Recordset()

Dim oAccess As New Access.Application()  

Dim DAO_DBEngine As New DAO.DBEngine()

'Press F12 to get help for any control on your form

Private Sub TestForm_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

  ' Establish DSN
  
  oAccess.DBEngine.RegisterDatabase("DCDM_Nwind", "Microsoft Access Driver (*.mdb)", True, "DBQ=" & VB6.GetPath & "\Nwind.mdb")

  CN.Open("DSN=DCDM_NWind")
  
  oOrders.Open("Orders", CN, oOrders.CursorType.adOpenKeyset, oOrders.LockType.adLockOptimistic)

  oOrderDetails.Open("OrderDetails", CN, oOrderDetails.CursorType.adOpenKeyset, oOrderDetails.LockType.adLockOptimistic)

  PopulateDate()

  Me.AxDataGrid1.DataSource = oOrderDetails

  HA.PrepareHelp(CN, Me, Me.AxDataGrid1)

End Sub
```
