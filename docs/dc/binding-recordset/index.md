# DC Binding Recordset 

## Overview

- DC.BindingRecordset is a high-performance COM-based component for environments like Visual Basic and Visual C++. It is only an 80 KB DLL, so it provides great speed and performance. It has all the magic, imagination, and incredible features you can find anywhere in the market.

- DC.BindingRecordset is an enhanced class that handles all aspects required for a data form, including single forms and master-detail forms. It handles all the required events so you rarely need to write additional code.

- The DC.BindingRecordset class is the best decision for software companies that need to develop applications quickly or depend on novice programmers. 

- Egy1ST has done a lot of work for you. You just need to define a few methods and properties of the DC.BindingRecordset class and we handle the rest.

## Features

Just a few lines in your Form_Load event give you full control over your form, all included elements (TextBox, Labels, Buttons, Grid, Recordset), and all related events (Leave, Paint, KeyPress, AfterColEdit, OnAddNew, Click, MouseEnter, MouseLeave, MouseDown, Enter). 

**You can:**

- Navigate first, previous, next, and last records.
- Add, edit, save, or delete records.  
- Set relations between master and detail tables.
- Retrieve related field names.
- Search data for specific criteria.  
- Trigger sensitive DataHelp for selection by pressing F1.
- Define required fields for data entry.
- Populate your form with data automatically when the focus changes.

**Note:** If you develop multi-language or Eastern language applications, it is recommended to use both DC.FormTranslator and DC.FormFlipper.

**Example:**

```vb
Dim BR As New DynamicComponents.BindingRecordset()  

' Establish DSN
oAccess.DBEngine.RegisterDatabase("DCDM_Nwind", "Microsoft Access Driver (*.mdb)", True, "DBQ=" & VB6.GetPath & "\Nwind.mdb")

CN.Open("DSN=DCDM_NWind")

oOrders.Open("Orders", CN, oOrders.CursorType.adOpenKeyset, oOrders.LockType.adLockOptimistic) 

oOrderDetails.Open("OrderDetails", CN, oOrderDetails.CursorType.adOpenKeyset, oOrderDetails.LockType.adLockOptimistic)

Me.AxDataGrid1.DataSource = oOrderDetails

BR.InitForm(CN, Me, oOrders, AxDataGrid1, oOrderDetails) 'Must Be your first declaration

BR.NavigationButtons("FirstButton", "PrevButton", "NextButton", "LastButton")

BR.ManipulationButtons("OkButton", "NewButton", "DeleteButton", "ExitButton", "SearchButton") 

BR.KeyFields("OrderId")  

BR.SetLink("OrderId", "OrderId")

BR.AddRelatedValue("Customers", "CustomerID", "CustomerID", "CustomerName", "xCustomerName", 3)

BR.AddRelatedValue("Shippers", "ShipperId", "ShipVia", "CompanyName", "xCompanyName", 2)  

BR.AddGridRelatedValue("Products", "ProductID", "ProductID", "ProductName", "ProductName", 2)

BR.KeyLeaveField(oOrders, "OrderId", 5) 

BR.RequiredFields("OrderId+OrderDate+CustomerId")

BR.PopulateForm(Me, oOrders, AxDataGrid1, oOrderDetails) 'Must be your last declaration
```

After these few lines you get full automated control of your form without writing any additional code. It's incredible!


## Convention  

There are two rules you must know about DC.BindingRecordset:

1. Textbox controls in your form must have the same names as their field names in the related table. Column controls in your grid must have the same names as their field names in the related detail table.

2. Textbox controls in your form that do not have a related field in the table must begin with "x" or "X". You cannot use "X" or "x" prefixes for related textbox controls.


## System Requirements

DC.BindingRecordset runs as a COM class for developing with Visual Basic.NET under Microsoft Windows 98/NT/2000 or Windows XP.

## Installing DC.BindingRecordset  

The DC.BindingRecordset setup program automatically registers the DC_BindingRecordset10.dll file on your system. There is no need to manually run RegSvr32.exe.

## Including DC.BindingRecordset

To include DC.BindingRecordset in your project:

1. From the Project menu select Add Reference.  
2. Click Browse to locate your DC_BindingRecordset10.DLL file which is located in [c:\windows\system32](file:///c:/windows/system32) by default. Now the DLL is included in your references.
3. Be sure Microsoft DataGrid Control Version 6.0 (OLEDB) is in your Toolbox. If not, right-click Toolbox, and select Customize Toolbox.
4. In the Customize Toolbox dialog, scroll down and check Microsoft DataGrid Control Version 6.0 (OLEDB).

## Deploying DC.BindingRecordset Applications   

The only file that needs distribution is DC_BindingRecordset10.dll. Copy this to C:\Windows\System32 by default.

**Note:** If you deploy a translated application with your local language, you must also deploy DCBR10_Lang.dll from [C:\Windows\System32](file:///C:/Windows/System32/) to the end user's system directory. 

## How to Create a DSN

1. Open Windows ODBC Data Source Administrator:
   - Windows 95/98/NT: Start > Settings > Control Panel > ODBC Data Sources icon.
   - Windows 2000: Start > Settings > Control Panel > Administrative Tools > Data Sources. 
   - Windows XP: Start > Control Panel > Performance and Maintenance > Administrative Tools > Data Sources (ODBC).

2. Click the System DSN tab. This displays your current DSNs.

3. Click Add to add a new DSN. The Create New Data Source dialog appears.

4. Select a driver and click Finish. For a Microsoft Access database, select Microsoft Access Driver (*.mdb). If your driver is not listed, you'll need to download and install it.

5. In the next dialog, enter a DSN name and connection parameters. For Microsoft Access, enter a name, click Select, locate the database file, and click OK.

6. Click OK to close the dialog. The new DSN is added.

### InitForm

Prepares the form, controls, and binding data. This must be the first assignment in your code or errors may occur. 

**Syntax:**

```vb
Function InitForm(ByRef dm_DSN As ADODB.Connection, ByRef dm_Form As System.Windows.Forms.Form, ByRef dm_MasterTable As ADODB.Recordset, Optional ByRef dm_Grid As AxMSDataGridLib.AxDataGrid = Nothing, Optional ByRef dm_DetailTable As ADODB.Recordset = Nothing)
```

Where:

- dm_DSN: Your DSN connection. 
- dm_Form: Your form passed as the 'Me' keyword.
- dm_MasterTable: Your master recordset.
- dm_Grid: Your grid (if applicable).  
- dm_DetailTable: Your detail recordset (if applicable).

**Example:**

```vb
Dim oMaster As New ADODB.Recordset()  

Dim oDetails As New ADODB.Recordset()

Dim DM As New DataManager()

Private Sub TestForm_Load() 

  CN.Open("DSN=NorthWind")
  
  oMaster.Open("Orders", CN, oMaster.CursorType.adOpenKeyset, oMaster.LockType.adLockOptimistic)

  oDetails.Open("OrderDetails", CN, oDetails.CursorType.adOpenKeyset, oDetails.LockType.adLockOptimistic)

  DM.InitForm(CN, Me, oMaster, AxDataGrid1, oDetails)

End Sub
```

### KeyFields

Assigns non-duplicate key fields. 

**Syntax:** 

```vb
Function KeyFields(ByVal str_KeyFields As String) 
```

**Note:** Concatenate multiple fields with '+'.

**Example:**

```vb
DM.KeyFields("Flag+OrderId") 
```

### KeyLeaveField  

Retrieves new data when focus changes from the specified field.

**Syntax:**

```vb
Function KeyLeaveField(ByRef dm_MasterTable As ADODB.Recordset, ByVal str_KeyLeaveField As String, Optional ByVal n_ZeroPad As Byte = 0)
```

**Note:** 

- n_ZeroPad pads with leading 0s, e.g. '0034'. This is useful for indexing/searching.
- n_ZeroPad is optional.

**Example:** 

```vb
DM.KeyLeaveField(oMaster, "OrderId", 5)
```

### SetLink

Links master fields to detail fields.

**Syntax:** 

```vb 
Function SetLink(ByVal str_MasterFields As String, ByVal str_DetailFields As String)
```

**Note:** Concatenate multiple fields with '+'.

**Example:**

```vb
DM.SetLink("Flag+OrderId", "Flag+OrderId")  
```

### AddRelatedValue

Retrieves the related value for a field.

**Syntax:**

```vb
Function AddRelatedValue(ByRef str_Table As String, ByVal str_Key As String, ByVal str_Control As String, ByVal str_RetValue As String, ByVal str_RetControl As String, Optional ByVal n_ZeroPad As Byte = 0) 
```

**Note:**  

- n_ZeroPad pads with leading 0s, e.g. '0034'. This is useful for indexing/searching.
- n_ZeroPad is optional.

**Example:** 

```vb
DM.AddRelatedValue("Customers", "CustomerID", "CustomerID", "CustomerName", "xCustomerName", 3)
```

### AddGridRelatedValue

Retrieves the related value for a grid column. 

**Syntax:**

```vb  
Function AddGridRelatedValue(ByVal str_Table As String, ByVal str_TableKey As String, ByVal str_Column As String, ByVal str_TableRetField As String, ByVal str_GridRetColumn As String, ByVal n_ZeroPad As Byte)
```

**Note:**  

- n_ZeroPad pads with leading 0s, e.g. '0034'. This is useful for indexing/searching.

**Example:**

```vb
DM.AddGridRelatedValue("Products", "ProductID", "ProductID", "ProductName", "ProductName", 2) 
```

### FlagField

Supports tables with a flag field, like "Personal" table with Customers as 1, Suppliers as 2, etc.

**Syntax:**  

```vb
Function FlagField(ByVal str_MasterFlagField As String, ByVal str_DetailFlagField As String, ByVal str_FlagValue As String)
```

**Example:**

```vb 
DM.FlagField("Flag","Flag","2")
```

### How to Select Some Fields  

Select only some detail table fields:

**Example:** 

```vb
oDetails.Open("select flag , billno , custno , custname , price from OrderDetails", CN, oDetails.CursorType.adOpenKeyset, oDetails.LockType.adLockOptimistic)
```

That's all!

### Search  

1. Click the search button to enter Search Mode, clearing the form. 
2. Enter search pattern and click Search again to view results.
3. Navigate through search results with the Navigation Buttons.  
4. Click Search twice to return to Normal Mode.

Notify the Manipulation Buttons function with the Search Button name.

### PopulateForm

Populates the form and grid with data. Recommended as the last assignment in Form_Load.

**Syntax:** 

```vb
Function PopulateForm(ByRef dm_Form As System.Windows.Forms.Form, ByRef dm_MasterTable As ADODB.Recordset, Optional ByRef dm_Grid As AxMSDataGridLib.AxDataGrid = Nothing, Optional ByRef dm_DetailTable As ADODB.Recordset = Nothing)
```

**Example:**

```vb
DM.PopulateForm(Me, oMaster, AxDataGrid1, oDetails)
```

### RequiredFields 

Assigns required fields that cannot be empty.

**Syntax:**

```vb 
Function RequiredFields(ByVal str_RequiredFields As String)
```

**Note:** Concatenate multiple fields with '+'.

**Example:** 

```vb
DM.RequiredFields("OrderId+OrderDate+CustomerId") 
```

### Sensitive F1 DataHelp

When you AddRelatedValue and focus is on the defined control:

1. Leaving the control retrieves the related value. 
2. Pressing F1 triggers a DataHelp browser to select a value.

When you AddGridRelatedValue and focus is on the defined column: 

1. Leaving the column retrieves the related value.
2. Pressing F1 triggers a DataHelp browser to select a value.

### NavigationButtons  

**Syntax:** 

```vb
Public Sub NavigationButtons(ByVal dm_First As String, ByVal dm_Previous As String, ByVal dm_Next As String, ByVal dm_Last As String)
```

**Example:**

```vb
DM.NavigationButtons("FirstButton", "PrevButton", "NextButton", "LastButton") 
```

### ManipulationButtons

**Syntax:**  

```vb  
Function ManipulationButtons(ByVal dm_Save As String, ByVal dm_New As String, ByVal dm_Delete As String, ByVal dm_Close As String, Optional ByVal dm_Search As String = Nothing) 
```

**Example:**

```vb
DM.ManipulationButtons("OkButton", "NewButton", "DeleteButton", "ExitButton", "SearchButton")
```

### Configuration Utility

Assign your own language:

![Config Utility](images//Aspose.Words.3e6e4189-8ddd-450c-b7ca-ac78dd84a3f2.004.png)

## Tutorial

See the full tutorial installed here:

C:\Program Files\Dynamic Components\Binding Recordset\Tutorial\

```vb
Dim BR As New DynamicComponents.BindingRecordset()

Dim CN As New ADODB.Connection()  

Dim oOrders As New ADODB.Recordset()

Dim oOrderDetails As New ADODB.Recordset()  

Dim oAccess As New Access.Application()

Dim DAO_DBEngine As New DAO.DBEngine()


Private Sub TestForm_Load()

  ' Establish DSN

  oAccess.DBEngine.RegisterDatabase("DCDM_Nwind", "Microsoft Access Driver (*.mdb)", True, "DBQ=" & VB6.GetPath & "\Nwind.mdb")

  CN.Open("DSN=DCDM_NWind")

  oOrders.Open("Orders", CN, oOrders.CursorType.adOpenKeyset, oOrders.LockType.adLockOptimistic)

  oOrderDetails.Open("OrderDetails", CN, oOrderDetails.CursorType.adOpenKeyset, oOrderDetails.LockType.adLockOptimistic)

  Me.AxDataGrid1.DataSource = oOrderDetails

  BR.InitForm(CN, Me, oOrders, AxDataGrid1, oOrderDetails) 'Must Be your first declaration

  BR.NavigationButtons("FirstButton", "PrevButton", "NextButton", "LastButton")

  BR.ManipulationButtons("OkButton", "NewButton", "DeleteButton", "ExitButton", "SearchButton")

  BR.KeyFields("OrderId")

  BR.SetLink("OrderId", "OrderId")

  BR.AddRelatedValue("Customers", "CustomerID", "CustomerID", "CustomerName", "xCustomerName", 3)

  BR.AddRelatedValue("Shippers", "ShipperId", "ShipVia", "CompanyName", "xCompanyName", 2)

  BR.AddGridRelatedValue("Products", "ProductID", "ProductID", "ProductName", "ProductName", 2)

  BR.KeyLeaveField(oOrders, "OrderId", 5)

  BR.RequiredFields("OrderId+OrderDate+CustomerId")

  BR.PopulateForm(Me, oOrders, AxDataGrid1, oOrderDetails) 'Must be your last declaration

End Sub
```
