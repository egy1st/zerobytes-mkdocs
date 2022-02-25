# DC Binding Recordset

Powered by ![](images/Aspose.Words.3e6e4189-8ddd-450c-b7ca-ac78dd84a3f2.001.png)



## Overview

- DC.BindingRecordset  is a high-performance COM-based environments such as Visual Basic, Visual C++ , it is only 80 KB DLL , so enjoy speed performance. it has all the magic ,imaginary and incredible features you can find any where in the market.
- DC.BindingRecordsetis is an enhanced class that handles all aspects required with a data form (including single form and master-details form. It handles all the events required that you rarely need few lines of additional programming code.
- DC.BindingRecordsetclass is the best decision for software companies  which need programming on no time or companies depends on novice programmers .
- Egy1ST has done a lot of work for you. You define few methods and properties of  DC.BindingRecordset class and we do the rest.

## Features

Few  Lines to add in your Form\_Load event  and you will get full control over your form and all included (TextBox - Lables-Buttons-Grid-Recordset) and all related events (Leave-paint-Keypress-AfterColEdit-OnAddNew-Click-MouseEnter-MouseLeave-MouseDown-Enter)

**You can:**

- Navigate first ,previous , next and last 
- Add new records ,edit it ,save it , or delete it 
- Set relation between master and details files
- Retrieve related names to your fields code 
- search data for specific formula
- Trigger sensitive DataHelp to select from by pressing F1 
- Define required Fields to accept input
- Populate your form with data automatically after focus change

**Note:**
if you develop multi language application or eastern language application , it is recommended to use both of DC.FormTranslator and DC.FormFlipper

**Example:**

Dim BR As New DynamicComponents.BindingRecordset()

'establish DSN

oAccess.DBEngine.RegisterDatabase("DCDM\_Nwind", "Microsoft Access Driver (\*.mdb)", True, "DBQ=" & VB6.GetPath & "\Nwind.mdb")

CN.Open("DSN=DCDM\_NWind")

oOrders.Open("Orders", CN, oOrders.CursorType.adOpenKeyset, oOrders.LockType.adLockOptimistic)

oOrderDetails.Open("OrderDetails", CN, oOrderDetails.CursorType.adOpenKeyset, oOrderDetails.LockType.adLockOptimistic)

Me.AxDataGrid1.DataSource = oOrderDetails

BR.[InitForm](#chmtopic10)(CN, Me, oOrders, AxDataGrid1, oOrderDetails) 'Must Be your first declaration

BR.[NavigationButtons](#chmtopic31)("FirstButton", "PrevButton", "NextButton", "LastButton")

BR.[ManipulationButtons](#chmtopic23)("OkButton", "NewButton", "DeleteButton", "ExitButton", "SearchButton")

BR.[KeyFields](#chmtopic11)("OrderId")

BR.[SetLink](#chmtopic13)("OrderId", "OrderId")

BR.[AddRelatedValue](#chmtopic14)("Customers", "CustomerID", "CustomerID", "CustomerName", "xCustomerName", 3)

BR.[AddRelatedValue](#chmtopic14)("Shippers", "ShipperId", "ShipVia", "CompanyName", "xCompanyName", 2)

BR.[AddGridRelatedValue](#chmtopic15)("Products", "ProductID", "ProductID", "ProductName", "ProductName", 2)

BR.[KeyLeaveField](#chmtopic12)(oOrders, "OrderId", 5)

BR.[RequiredFields](#chmtopic20)("OrderId+OrderDate+CustomerId")

BR.[PopulateForm](#chmtopic19)(Me, oOrders, AxDataGrid1, oOrderDetails) 'Must be your last declaration

after this few lines you will get full automated controling on your form without any additional code to write , it is incredible !


## Convention

There are Two  Rules you must know about DC.BindingRecordset

1. ` `Textbox Controls which located in your data form must have the same names as their Fields names in related table and Columns Controls which involved in your datagrid must have the same names as their Fields names in related table for details
1. Textbox Controls which located in your data form and not have related Field in related table must begin with "x" or "X" character , you can not name related Textbox Control with "X" or "x" prefix




## System Requirements 

DC.BindingRecordsetruns as a COM class for Developing with Visual Basic.Net under Microsoft Windows 98/NT/ 2000 or Windows XP. 


**Installing DC.BindingRecordset**
The DC.DataManger setup program will automatically register the DC\_DataManger10.dll file on your system. 
There is no need to manually run RegSvr32.exe on your development system. 

## Including DC.BindingRecordset

To include DC.BindingRecordset in your project 

1. From Project menu select add reference 
1. Push Browse button to locate your DC\_BindingRecordset10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32)  , now the specific DLL included in your references
1. Be sure that Micorsoft DataGrid Control Vresion 6.0 (OLEDB) is included in your Toolbox , if not then right click Toolbox 
1. From shortcut menu select customize Toolbox
1. From customize Toolbox Dialog ,scroll down and check Micorsoft DataGrid Control Version 6.0 (OLEDB)


## Deploying DC.BindingRecordsetApplications

The only file needs to be distributed with DC.BindingRecordset COM applications is DC\_BindingRecordset10.dll
this file should be copied to the WinSystem directory which by default is C:\Windows\System32 

**Note :** 

If you deploy a translated application with your local language , you must deploy DCBR10\_Lang.dll which located in your system directory which is by default [C:\Windows\System32\](file:///C:/Windows/System32/)  and place it in end user system directory

## How to Create a DSN

1. Open Windows’ ODBC Data Source Administrator as follows:
   In Windows 95, 98, or NT, choose Start > Settings > Control Panel, then double-click the ODBC Data     
   Sources icon. Depending on your system, the icon could also be called ODBC or 32bit ODBC.
   in Windows 2000, choose Start > Settings > Control Panel > Administrative Tools > Data Sources.
   In Windows XP, choose Start > Control Panel > Performance and Maintenance > Administrative Tools >   
   Data Sources (ODBC).

2. Click the System DSN tab.
   The tab displays the list of DSNs currently on your system. 

3. Click Add to add a new DSN to the list.
   The Create New Data Source dialog box appears, listing all the drivers currently loaded on your system. 

4. Select a driver from the list, then click Finish

**Example:**

If your database is a Microsoft Access file, select Microsoft Access Driver (\*.mdb). If a driver for your product does not appear in the list, you’ll have to download the driver from a vendor’s website and install it. 

In the dialog box that appears, enter a name for the DSN and specify the connection parameters.

The dialog boxes for specifying parameters differ depending on the driver you selected. For the Microsoft Access Driver, you enter a name, click Select, locate the database file on the hard disk, and click OK. 

Click OK to close the dialog box.

The new DSN is added to your list of system DSNs. 


### InitForm

Prepare form to know every thing about the form and its controls and all binding data . so it must be the first assignment in your code . an errors may occurs if you do not

**syntax:**

>  Function InitForm (ByRef dm\_DSN As ADODB.Connection, ByRef dm\_Form As System.Windows.Forms.Form, ByRef dm\_MasterTable As ADODB.Recordset, Optional ByRef dm\_Grid As AxMSDataGridLib.AxDataGrid = Nothing, Optional ByRef dm\_DetailTable As ADODB.Recordset = Nothing)

dm\_DSN  is a reference to your DSN connection

dm\_Form is a reference to your form which passed as 'Me' keyword

dm\_MasterTable is a reference to your Master Recordset

Optional dm\_Grid (if your form has a grid) is a reference to your grid

Optional dm\_DetailTable (if your form has a grid) is a reference to your Details Recordset

**Example:**

> Dim oMaster As New ADODB.Recordset()
>
> Dim oDetails As New ADODB.Recordset()
>
> Dim DM As New DataManger()



Private Sub TestForm\_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

CN.Open("DSN=NorthWind")

oMaster.Open("Orders", CN, oMaster.CursorType.adOpenKeyset, oMaster.LockType.adLockOptimistic)

oDetails.Open("OrderDetails", CN, oDetails.CursorType.adOpenKeyset, oDetails.LockType.adLockOptimistic)

DM.InitForm(CN, Me, oMaster, AxDataGrid1, oDetails)

End Sub

### KeyFields

it assigns the fields in your Recordset which not allowed to duplicate

**Syntax:**

Function KeyFields(ByVal str\_KeyFields As String)

**Note:**

multi fields can concatenated by plus sign '+'

**Example:**

DM.KeyFields("Flag+OrderId")

### KeyLeaveField

` `it assigns the fields in your Recordset which will retieve new data when focus chang away from it

**Syntax:**

Function  KeyLeaveField(ByRef dm\_MasterTable As ADODB.Recordset, ByVal str\_KeyLeaveField As String, Optional ByVal n\_ZeroPad As Byte = 0)

![](images/Aspose.Words.3e6e4189-8ddd-450c-b7ca-ac78dd84a3f2.002.png)

**Note:**

n\_ZeroPad parameter padding data with "0" character

this mean that '34' with  n\_ZeroPad is 4 will be '0034' 

this is useful for indexing and searching purposes if you want , remember that is an optional parameter

**Example:**

DM.KeyLeaveField(oMaster, "OrderId", 5)

### SetLink

It assigns the fields in your Master Recordset which are linked to related fields in Details Recordset

**Syntax:**

Function Sub SetLink(ByVal str\_MasterFields As String, ByVal str\_DetailFields As String)

**Note:**

**multi fields can concatenated by plus sign '+'**

**Example:**

DM.SetLink("Flag+OrderId", "Flag+OrderId")


### AddRelatedValue

Retrieve the related value to your field code 
assume you save Cust\_Code in your master recordset 
when you retrieve data you also want to get Cust\_Name form Customers table . AddRelatedValue Function do that for you easily

![](images/Aspose.Words.3e6e4189-8ddd-450c-b7ca-ac78dd84a3f2.002.png)

**Syntax:**

> Function AddRelatedValue(ByRef str\_Table As String, ByVal str\_Key As String, ByVal str\_Control As String, ByVal str\_RetValue As String, ByVal str\_RetControl As String, Optional ByVal n\_ZeroPad As Byte = 0)



**Note:**

- n\_ZeroPad parameter padding data with "0" character

- this mean that '34' with  n\_ZeroPad is 4 will be '0034' 

- this is useful for indexing and searching purposes if you want , remember that is an optional parameter



**Example:**

DM.AddRelatedValue("Customers", "CustomerID", "CustomerID", "CustomerName", "xCustomerName", 3)




### AddGridRelatedValue

It retrieve the related value to your grid field code

assume you save Productt\_Code in your Detail recordset

when you retrieve data you also want to get Product\_Name form Products table . AddRelatedValue Function do that for you easily

![](images/Aspose.Words.3e6e4189-8ddd-450c-b7ca-ac78dd84a3f2.002.png)



**Syntax:**

>  Function AddGridRelatedValue(ByVal str\_Table As String, ByVal str\_TableKey As String, ByVal str\_Column As String, ByVal str\_TableRetField As String, ByVal str\_GridRetColumn As String, ByVal n\_ZeroPad As Byte)
>
>  

**Note:**

- n\_ZeroPad parameter padding data with "0" character

- this mean that '34' with  n\_ZeroPad is 4 will be '0034' 

- this is useful for indexing and searching purposes if you want , remember that is an optional parameter



**Example:**

DM.AddGridRelatedValue("Products", "ProductID", "ProductID", "ProductName", "ProductName", 2)

### FlagField

Sometimes you use table which involve multi tables within , as "Personal" table which can involve "Customers", "Suppliers" , "Debits" , "Credits" with different flag key 

you can assign value "1" for Customers ,  assign value "2" for Suppliers and so on

the rest of fields is the same.

We support Tables with Flag field 



**Syntax:**

>  Function FlagField(ByVal str\_MasterFlagField As String, ByVal str\_DetailFlagField As String, ByVal str\_FlagValue As String)



**Example:**

DM.FlafField("Flag","Flag","2")



### How to select some fields

Sometimes you want to include some fields of your detail table , not all its fields
the next example do that 

**Example:**

oDetails.Open("select flag , billno , custno , custname , price from OrderDetails", CN, oDetails.CursorType.adOpenKeyset, oDetails.LockType.adLockOptimistic)

**That is all !**



### Search

Easily to search your recordset , add button in your form and notify [Manipulation Buttons ](#chmtopic22)Function with its name

1. Begin search by clicking search button , all form controls will be empty , now you get in Search Mode
1. Enter your pattern to search and click search button again , now your form has the search result
1. Navigate through records which apply your search pattern by[Navigation Buttons](#chmtopic22)
1. Return to Normal Mode by click search button twice

![](images/Aspose.Words.3e6e4189-8ddd-450c-b7ca-ac78dd84a3f2.002.png)

### PopulateForm 

it populates your form and its grid with data

it is recomended to be last assignment in your Form\_Load event 

**Syntax:**

>  Function PopulateForm(ByRef dm\_Form As System.Windows.Forms.Form, ByRef dm\_MasterTable As ADODB.Recordset, Optional ByRef dm\_Grid As AxMSDataGridLib.AxDataGrid = Nothing, Optional ByRef dm\_DetailTable As ADODB.Recordset = Nothing)



**Example:**

DM.PopulateForm(Me, oMaster, AxDataGrid1, oDetails)

### RequiredFields

it assigns the fields in your Recordset which can not be empty

**Syntax:**

Function RequiredFields(ByVal str\_RequiredFields As String)

**Note:**

multi fields can concatenated by plus sign '+'

**Example:**

DM.RequiredFields("OrderId+OrderDate+CustomerId")

### Sensitive F1 DataHelp

When you [AddRelatedValue](#chmtopic14) and your focus is located in the control defined in str\_Control (which is control came) parameter you get 2 magic advantages.

1. When you leave from this control you will retrieve respected value related to this control value 
1. When you press F1 Key this will trigger DataHelp Browser filled with the table defined in str\_Table parameter , you can select any row by double click it , this will close DataHelp Browser and assigned the data selected to the control defined in str\_RetControl parameter



When you [AddGridRelatedValue](#chmtopic15) and your focus is located in the column defined in str\_Column (which is Column name) parameter you get 2 magic advantages.

1. When you leave from this control you will retrieve respected value related to this control value
1. When you press F1 Key this will trigger DataHelp Browser filled with the table defined in str\_Table parameter , you can select any row by double click it , this will close DataHelp Browser and assigned the data selected to the column defined in str\_GridRetColumn parameter


### NavigationButtons

Assign Navigation Buttons names so that DC DataManger do all required with it

**Note:**

Navigation Buttons are Buttons which enable you navigate through recordset by moving it first , previous . next and last .

![](images/Aspose.Words.3e6e4189-8ddd-450c-b7ca-ac78dd84a3f2.003.png)

**Syntax:**

> Public Sub NavigationButtons(ByVal dm\_First As String, ByVal dm\_Previous As String, ByVal dm\_Next As String, ByVal dm\_Last As String)



**Example:**

DM.NavigationButtons("FirstButton", "PrevButton", "NextButton", "LastButton")

### ManipulationButtons

Assign Manipulation Buttons names so that DC DataManger do all required with it

**Note:**

Manipulation Buttons are Buttons which enable you add , edit , save or delete records in your recordset .

![](images/Aspose.Words.3e6e4189-8ddd-450c-b7ca-ac78dd84a3f2.002.png)



**Syntax:**

>  Function ManipulationButtons(ByVal dm\_Save As String, ByVal dm\_New As String, ByVal dm\_Delete As String, ByVal dm\_Close As String, Optional ByVal dm\_Search As String = Nothing)



**Example:**

DM.ManipulationButtons("OkButton", "NewButton", "DeleteButton", "ExitButton", "SearchButton")

### Configuration Utility

-----

We supply you with Configuration Utility which enable you to assign your own language used with DC.DataManger 

![](images/Aspose.Words.3e6e4189-8ddd-450c-b7ca-ac78dd84a3f2.004.png)




## Tutorial

This tutorial describe most of features supported by DC.BindingRecordset

also you can refer to the project  example which installed by default into C:\Program Files\Dynamic Components\Binding Recordset\Tutorial\

``` vb
Dim BR As New DynamicComponents.BindingRecordset()

Dim CN As New ADODB.Connection()

Dim oOrders As New ADODB.Recordset()

Dim oOrderDetails As New ADODB.Recordset()

Dim oAccess As New Access.Application()

Dim DAO\_DBEngine As New DAO.DBEngine()



Private Sub TestForm\_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

'establish DSN

oAccess.DBEngine.RegisterDatabase("DCDM\_Nwind", "Microsoft Access Driver (\*.mdb)", True, "DBQ=" & VB6.GetPath & "\Nwind.mdb")

CN.Open("DSN=DCDM\_NWind")

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