# DC Data Manager

## Overview

DC.DataManger is a high-performance COM-based environment such as Visual Basic, and Visual C++, It is only 80 KB DLL, so enjoy speed performance.

DC.DataManger class has all the magic, imaginary, and incredible features you can find anywhere in the market. 

DC.DataManger is an enhanced class that handles all aspects required with a data form (including single form and master-details form).

DC.DataManger class handles all the events required and you rarely need a few lines of additional programming code.

DC.DataManger class is the best decision for software companies that need programming in no time or companies that depend on novice programmers.

EgyFirst has done a lot of work for you. You define a few methods and properties of DC.DataManger classand wedo the rest.

## Features

Few Lines to add in your Form_Load event and you will get full control over your form and all included (TextBox - Lables-Buttons-Grid-Recordset) and all related events (Leave-paint-Keypress-AfterColEdit-OnAddNew-Click-MouseEnter-MouseLeave-MouseDown-Enter)

You can:

- Navigate first ,previous, next, and last
- Add new records,edit it , save it , or delete it
- Retrieve related names to your field code
- Trigger sensitive DataHelp to select from pressing F1
- Trigger sensitive Help by pressing F12
- Validate your entry by restricting it to a predefined type(Numeric-Alphabetic-AlphaNumeric-Date-Decimal) or to your defined characters
- Notify you with red forecolor if your entry is not proper  
- Format data by defining decimal places for numeric entry, or defining letter case for character entry
- Change button image according to mouse movement or focus change
- Support MultiLanguage Application , by populating form labels with predefined translation automatically
- Support Eastern Language, we support right-left application by changing alignment to right and orientation by flipping form horizontally 180
- Enable you to navigate through controls with the Return key as with the tab key

**Example:**

```
dm.[InitForm](#chmtopic10)(CN, Me, oMaster, AxDataGrid1, oDetails)

dm.[PrepareImageButtons](#chmtopic33)(aImage, "C:\DataManage\Icons\", False)

dm.[NavigationButtons](#chmtopic34)("FirstButton", "PrevButton", "NextButton", "LastButton")

dm.[ManageButtons](#chmtopic35)("OkButton", "NewButton", "DeleteButton", "ExitButton", "SearchButton")

dm.[KeyFields](#chmtopic11)("OrderId") 

dm.[SetLink](#chmtopic13)("OrderId", "OrderId")

dm.[AddRelatedValue](#chmtopic14)("Customers", "CustomerID", "CustomerID", "CustomerName", "xCustomerName", 3)

dm.[AddGridRelatedValue](#chmtopic15)("Products", "ProductID", "ProductID", "ProductName", "ProductName", 2)

dm.[KeyLeaveField](#chmtopic12)(oMaster, "OrderId", 5)

dm.[RequiredFields](#chmtopic27)("OrderId+OrderDate+CustomerId") 

dm.[NumericFields](#chmtopic20)("CustomerID", "OrderId", "ShipVia")

dm.[DateFields](#chmtopic23)("OrderDate")

dm.[PopulateForm](#chmtopic19)(Me, oMaster, AxDataGrid1, oDetails)
```

after these few lines, you will get full automated control on your form without any additional code to write, it is incredible!


## Convention

There are two Rules you must know about DC.DataManger

1. Textbox Controls which are located in your data form must have the same names as their field names in the related table and Columns Controls which are involved in your datagrid must have the same names as their field names in the related table for details
2. Textbox Controls located in your data form and not have related Fields in the related table must begin with "x" or "X" character, you can not name related Textbox Controls with "X" or "x" prefix

## System Requirements

DC.DataMangerruns as a COM class for Developing with Visual Basic.Net under Microsoft Windows 98/NT/ 2000 or Windows XP.

## Installing DC.DataManger

The DC.DataManger setup program will automatically register theDC_DataManger10.dll file on your system.

There is no need to manually run RegSvr32.exe on your development system.

## Including DC.DataManger 

To include DC.DataManger in your project:

1. From the Project menu select Add a reference
2. Push Browse button to locate your DC_DataManger10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32) , now the specific DLL included in your references 
3. Be sure that Microsoft DataGrid Control Version 6.0 (OLEDB) is included in your Toolbox, if not then right-click Toolbox
4. From the shortcut menu select Customize Toolbox 
5. From customize Toolbox Dialog, scroll down and check Microsoft DataGrid Control Version 6.0 (OLEDB)


## Deploying DC.DataManger Applications

The only file needs to be distributed with DC.DatManger COM applications is DC_DataManger10.dll. This file should be copied to the WinSystem directory which by default is C:\Windows\System32

**Note:** If you deploy a translated application with your local language, you must deploy DCDM10_Lang.dll which located in your system directory which is by default [C:\Windows\System32](file:///C:/Windows/System32/), and place it in end-user system directory

## How to Create a DSN

1. Open Windows’ ODBC Data Source Administrator as follows:

   In Windows 95, 98, or NT, choose Start > Settings > Control Panel, then double-click the ODBC Data Sources icon. Depending on your system, the icon could also be called ODBC or 32bit ODBC.

   In Windows 2000, choose Start > Settings > Control Panel > Administrative Tools > DataSources.

   In Windows XP, choose Start > Control Panel > Performance and Maintenance > Administrative Tools > Data Sources (ODBC).


2. Click the SystemDSNtab. The tab displays the list of DSNs currently on your system.

3. Click Add to add a new DSN to the list. The Create New Data Source dialog box appears, listing all the drivers currently loaded on your system.

4. Select a driver from the list, then click Finish

   **Example:** If your database is a Microsoft Access file, select Microsoft Access Driver (\*.mdb). If a driver for your product does not appear in the list, you’ll have to download the driver from a vendor’s website and install it.

   In the dialog box that appears, enter a name for the DSN and specify the connection parameters. The dialog boxes for specifying parameters differ depending on the driver you selected. For the Microsoft Access Driver, you enter a name, click Select, locate the database file on the hard disk, and click OK.

5. Click OK to close the dialog box. The new DSN is added to your list of system DSNs.

## InitForm

Prepare the form to know everything about the form its controls and all binding data. so it must be the first assignment in your code. an error may occurs if you do not

**Syntax:**

```
Function InitForm(ByRef dm_DSN As ADODB.Connection, ByRef dm_Form As System.Windows.Forms.Form, ByRef dm_MasterTable As ADODB.Recordset, Optional ByRef dm_Grid As AxMSDataGridLib.AxDataGrid = Nothing, Optional ByRef dm_DetailTable As ADODB.Recordset = Nothing)
```

- `dm_DSN` is a reference to your DSN connection
- `dm_Form` is a reference to your form which passed as the 'Me' keyword
- `dm_MasterTable` is a reference to your Master Recordset  
- Optional `dm_Grid` (if your form has a grid) is a reference to your grid
- Optional `dm_DetailTable` (if your form has a grid) is a reference to your Details Recordset

**Example:**

```
Dim oMaster As New ADODB.Recordset()  

Dim oDetails As New ADODB.Recordset()

Dim DM As New DataManger()

Private Sub TestForm_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

  CN.Open("DSN=NorthWind")
  
  oMaster.Open("Orders", CN, oMaster.CursorType.adOpenKeyset, oMaster.LockType.adLockOptimistic)
  
  oDetails.Open("OrderDetails", CN, oDetails.CursorType.adOpenKeyset, oDetails.LockType.adLockOptimistic)

  DM.InitForm(CN, Me, oMaster, AxDataGrid1, oDetails)
  
End Sub
```

## KeyFields

It assigns the fields in your Recordset which not allowed to duplicate

**Syntax:** 

`Function KeyFields(ByVal str_KeyFields As String)`

**Note:**

multi fields can concatenated by the plus sign '+'

**Example:**

`DM.KeyFields("Flag+OrderId")`

## KeyLeaveField

It assigns the fields in your Recordset which will receive new data when the focus changes away from it

**Syntax:**

`Function KeyLeaveField(ByRef dm_MasterTable As ADODB.Recordset, ByVal str_KeyLeaveField As String, Optional ByVal n_ZeroPad As Byte = 0)`

**Note:** 

`n_ZeroPad` parameter padding data with "0" character. This means that '34' with `n_ZeroPad` is 4 will be '0034'. This is useful for indexing and searching purposes if you want, remember that is an optional parameter

**Example:** 

`DM.KeyLeaveField(oMaster, "OrderId", 5)`

## SetLink

It assigns the fields in your Master Recordset which are linked to related fields inDetails Recordset

**Syntax:**

`Function Sub SetLink(ByVal str_MasterFields As String, ByVal str_DetailFields As String)`

**Note:** 

multi fields can concatenated by the plus sign '+'

**Example:**

`DM.SetLink("Flag+OrderId", "Flag+OrderId")`

## AddRelatedValue

Retrieve the related value to your field code. Assume you save Cust_Code in your master recordset. When you retrieve data you also want to get Cust_Name from the Customers table. AddRelatedValue Function does that for you easily.

**Syntax:**

```
Function AddRelatedValue(ByRef str_Table As String, ByVal str_Key As String, ByVal str_Control As String, ByVal str_RetValue As String, ByVal str_RetControl As String, Optional ByVal n_ZeroPad As Byte = 0) 
```

**Note:** 

`n_ZeroPad` parameter padding data with "0" character. This means that '34' with `n_ZeroPad` is 4 will be '0034'. This is useful for indexing and searching purposes if you want, remember that is an optional parameter


**Example:** 

`DM.AddRelatedValue("Customers", "CustomerID", "CustomerID", "CustomerName", "xCustomerName", 3)`


# AddGridRelatedValue

It retrieve the related value to your grid field code. Assume you save Productt_Code in your Detail recordset. When you retrieve data you also want to get Product_Name from the Products table. AddRelatedValue Function does that for you easily.

**Syntax:**

```
Function AddGridRelatedValue(ByVal str_Table As String, ByVal str_TableKey As String, ByVal str_Column As String, ByVal str_TableRetField As String, ByVal str_GridRetColumn As String, ByVal n_ZeroPad As Byte)
```

**Note:** 

`n_ZeroPad` parameter padding data with "0" character. This means that '34' with `n_ZeroPad` is 4 will be '0034'. This is useful for indexing and searching purposes if you want, remember that is an optional parameter.

**Example:**

```
DM.AddGridRelatedValue("Products", "ProductID", "ProductID", "ProductName", "ProductName", 2)
```

# FlagField

Sometimes you use a table that involves multiple tables within, such as a "Personal" table which can involve "Customers", "Suppliers", "Debits", and "Credits" with different flag keys. You can assign the value "1" for Customers, assign the value "2" for Suppliers, and so on. The rest of the fields are the same.

We support Tables with the Flag field

**Syntax:** 

```
Function FlagField(ByVal str_MasterFlagField As String, ByVal str_DetailFlagField As String, ByVal str_FlagValue As String)
```

**Example:** 

`DM.FlafField("Flag","Flag","2")`

# How to select some fields

Sometimes you want to include some fields of your detail table, not all of its fields. The next example is that:

**Example:**

```
oDetails.Open("select flag, billno, custno, custname, price from OrderDetails", CN, oDetails.CursorType.adOpenKeyset, oDetails.LockType.adLockOptimistic)
```

That is all!

# Search 

Easily to search your recordset, add a button in your form and notify [Manipulation Buttons](#chmtopic34) Function with its name

1. Begin search by clicking the search button, All form controls will be empty, and now you get into Search Mode
2. Enter your pattern to search and click the search button again, now your form has the search result  
3. Navigate through records that apply your search pattern by [Navigation Buttons](#chmtopic34)
4. Return to Normal Mode by clicking the search button twice

# PopulateForm

It populates your form and its grid with data. It is recommended to be the last assignment in your Form_Load event.

**Syntax:** 

```
Function PopulateForm(ByRef dm_Form As System.Windows.Forms.Form, ByRef dm_MasterTable As ADODB.Recordset, Optional ByRef dm_Grid As AxMSDataGridLib.AxDataGrid = Nothing, Optional ByRef dm_DetailTable As ADODB.Recordset = Nothing)
```

**Example:**

`DM.PopulateForm(Me, oMaster, AxDataGrid1, oDetails)`

# NumericFields

It restricts data entry to only valid entries. Valid entry may be one or more of the allowed characters which is"0123456789".

**Syntax:**

`Function NumericFields(ByVal ParamArray str_NumericFields() As String)` 

**Note:** Multi fields can concatenated by comma ","

**Example:** 

`DM.NumericFields("CustomerID", "OrderId", "ShipVia")`

# AlphabeticFields

It restricts data entry to only valid entries. Valid entry may be one or more of the allowed characters which are "abcdefghijklmnopqrstuvwxyz" additional to upper case "ABCDEFGHIJKLMNOPQRSTUVWXYZ".

**Syntax:**

`Function AlphabeticFields(ByVal ParamArray str_NumericFields() As String)`

**Note:** Multi fields can concatenated by comma ","

**Example:** 

`DM.NumericFields("FirstName", "FamilyName")`

# AlphaNumericFields 

It restricts data entry to only valid entries. Valid entry may be one or more of the allowed characters which is"abcdefghijklmnopqrstuvwxyz" and upper case "ABCDEFGHIJKLMNOPQRSTUVWXYZ" additional to numeric characters "0123456789".

**Syntax:** 

`Function AlphaNumericFields(ByVal ParamArray str_NumericFields() As String)`

**Note:** Multi fields can concatenated by comma ","

**Example:**

`DM.NumericFields("Address")`

# DateFields

It restricts data entry to only valid entries. Valid entry may be one or more of the allowed characters which are "0123456789" additional to "/-\" characters. When you leave the edited Textbox if the data entry is not a date you will be notified by changing the forecolor to red color until you re-edit it correctly.

Suppose you enter a date like "30/2/2004". This is an invalid entry, so you will be notified by changing the color to red.

**Syntax:** 

`FunctionDateFields(ByVal ParamArray str_DateFields() As String)` 

**Note:** Multi fields can concatenated by comma ","

**Example:**

`DM.DateFields("OrderDate")`

# DecimalFields

It restricts data entry to only valid entries. Valid entry may be one or more of the allowed characters which are "0123456789" additional to decimal point '.'. Data entry will be formatted by n decimal places defined in [DecimalPlaces](#chmtopic30) Function. When you leave the edited Textbox if the data entry is not a date you will be notified by changing forecolor to red color until you re-edit it correctly.

Suppose you enter a date like "705.3.2". This is an invalid entry, so you will be notified by changing the color to red.

**Syntax:**

`Function DecimalFields(ByVal ParamArray str_NumericFields() As String)` 

**Note:** Multi fields can concatenated by comma ","  

**Example:**

`DM.DecimalFields("Freight")`

# SpecialChars

It restricts data entry to only valid entries. Valid entry may be one or more of the characters which are contained in its parameter.

**Syntax:** 

`Function SpecialChars(ByVal str_Chars As String)`

**Example:** 

`DM.SpecialChars ("YyNn")`

# SpecialCharsFields

It restricts data entry to only valid entries. Valid entry may be one or more of the characters that are contained in the [SpecialChars](#chmtopic25) function.

**Syntax:**

`Function SpecialCharsFields(ByVal ParamArray str_SpecialFields() As String)`

**Note:** Multi fields can concatenated by comma ","

**Example:** 

`DM.SpecialCharsFields ("Married")`

# RequiredFields 

It assigns the fields in your Recordset which can not be empty.

**Syntax:** 

`Function RequiredFields(ByVal str_RequiredFields As String)`

**Note:** Multi fields can concatenated by the plus sign '+'  

**Example:**

`DM.RequiredFields("OrderId+OrderDate+CustomerId")`

# LowerCaseFields

It converts all characters to lowercase. 

**Syntax:**

`Function LowerCaseFields(ByVal ParamArray str_LowerCaseFields() As String)`

**Note:** Multi fields can concatenated by comma ","

**Example:**

`DM.LowerCaseFields ("SupplierName")`

# UpperCaseFields

It converts all characters to upper case.

**Syntax:** 

`Function UpperCaseFields(ByVal ParamArray str_UpperCaseFields() As String)` 

**Note:** Multi fields can concatenated by comma ","

**Example:**

`DM.UpperCaseFields ("ProductName")`

# DecimalPlaces

It formats numbers by making it in the decimal state with n places which you define in your function.

**Syntax:**

`FunctionDecimalPlaces(ByVal n_DecimalPlaces As Byte)`

**Example:** 

`DM.DecimalPlaces(2)`

# FirstCharOnlyFields

It converts only the First character to upper case.

**Syntax:** 

`FunctionFirstCharOnlyFields(ByVal ParamArray str_FirstCharOnlyFields() As String)`

**Note:** Multi fields can concatenated by comma ","  

**Example:** 

`DM.FirstCharOnlyFields ("CustomerName")`

# FirstCharOfWordsFields

It converts the First character of every word to upper case. 

**Syntax:**

`Function FirstCharOfWordsFields(ByVal ParamArray str_FirstCharOfWordsFields() As String)`

**Note:** Multi fields can concatenated by comma ","

**Example:** 

`DM.FirstCharOfWordsFields("CustomerName")`

# PrepareImageButtons

Your Data Form have [Navigation](#chmtopic34) & [Manipulation](#chmtopic35) Buttons. You can assign changeable icons for each button, additionally, you can assign a motion for each button if you put the third parameter to true, all you need is:

- Buttons without Motion

- Buttons with Motion

1. Declare an array with 27 element
2. Assign 3 icons for each button: 
   - First icon for MouseLeave state
   - Second icon for MoveOver state  
   - Third icon for MoveDown state
3. Populate your array respectively with icons as this sequence:

   ```
   FirstButton_MouseLeave , FirstButton_MouseOver, FirstButton_MouseDown
   
   PreviousButton_MouseLeave , PreviousButton_MouseOver, PreviousButton_MouseDown
   
   NextButton_MouseLeave , NextButton_MouseOver, NextButton_MouseDown
   
   LastButton_MouseLeave , LastButton_MouseOver, LastButton_MouseDown
   
   SavedataButton_MouseLeave , SavedataButton_MouseOver, SavedataButton_MouseDown
   
   NewdataButton_MouseLeave , NewdataButton_MouseOver, NewdataButton_MouseDown
   
   DeleteDataButton_MouseLeave , DeleteDataButton_MouseOver, DeleteDataButton_MouseDown
   
   CloseFormButton_MouseLeave , CloseFormButton_MouseOver, CloseFormButton_MouseDown
   
   and optionally you can add SearchButton_MouseLeave, SearchButton_MouseOver, SearchButton_MouseDown
   ```

**Syntax:**

`Function PrepareImageButtons(ByVal ImagesArray() As String, ByVal ImageFullPath As String, ByVal Motion As Boolean)`

**Example:**

```
DM.PrepareImageButtons(aImage, "C:\MyApp\Icons\", True)
```

Where `aImage` is your array holding icons. The third parameter indicates that you wish to show motion with each button.


# NavigationButtons

Assign Navigation Buttons names so that DC DataManger does all required with it

**Note:** 

Navigation Buttons are Buttons that enable you to navigate through recordset by moving it first, previous. next and last.

**Syntax:**

```
Public Sub NavigationButtons(ByVal dm_First As String, ByVal dm_Previous As String, ByVal dm_Next As String, ByVal dm_Last As String)
```

**Example:**

`DM.NavigationButtons("FirstButton", "PrevButton", "NextButton", "LastButton")`

# ManipulationButtons

Assign Manipulation Buttons names so that DC DataManger do all required with it

**Note:**

Manipulation Buttons are Buttons that enable you to add, edit, save, or delete records in your recordset.

**Syntax:**

```
Function ManipulationButtons(ByVal dm_Save As String, ByVal dm_New As String, ByVal dm_Delete As String, ByVal dm_Close As String, Optional ByVal dm_Search As String = Nothing)
```

**Example:** 

`DM.ManipulationButtons("OkButton", "NewButton", "DeleteButton", "ExitButton", "SearchButton")`

# Sensitive F1 DataHelp

When you [AddRelatedValue](#chmtopic14)and your focus is located in the control defined in the str_Control (which is the control name) parameter you get 2 magic advantages.

1. When you leave this control you will retrieve respected value related to this control value
2. When you press the F1 Key this will trigger the DataHelp Browser filled with the table defined in the str_Table parameter, You can select any row by double-clicking it , this will close the DataHelp Browser and assign the data selected to the control defined in the str_RetControl parameter

When you [AddGridRelatedValue](#chmtopic15)and your focus is located in the column defined in str_Column (which is the Column name)parameter you get 2 magic advantages.

1. When you leave this control you will retrieve respected value related to this control value  
2. When you press the F1 Key this will trigger the DataHelp Browser filled with the table defined in the str_Table parameter, you can select any row by double-clicking it , this will close the DataHelp Browser and assign the data selected to the column defined in the str_GridRetColumn parameter

# Sensitive F12 Help

When you press F12 Key, this triggers a sensitive help,this requires:

1. Create a new table, name it "Help" and put it in your database
2. create 4 fields as specified:

| Name | Type | Length |
|-|-|-|  
| Tag | Text | 50 |
| Id | Text | 50 |
| Description | Text | 50 |
| Contents | Memo | |

3. Fill Tag field with your [Form Tag](JavaScript:popup.TextPopup\(popuptxt1,popupfont1,9,9,-1,-1\)) 

4. Fill the Id Field with your control name

5. Fill the Id Field with the DataGrid name followed by the underscore character "_", which will be something like this:

`"axDatagrid_ProductId"`

6. Fill Description field with your control Description  

7. Fill Contents field with your supported help for this control

**Note:** To change your form text put the form name in both the field tag and id

# TranslateForm

We support Multi-Language Applications, you can use the same application with different languages. All you need is:

1. Create a new table, name it "Multilanguage" and put it in your database
2. create 4 fields as specified:

|Name|Type|Length|  
|-|-|-|
|Tag|Text|50|
|Id|Text|50|  
|Language1|Text|50|
|Language2|Text|50|

3. Fill Tag field with your Form Name 

4. Fill the Id Field with your Label name

5. Fill Language1 field with your first language translation  

6. Fill the Language2 field with your second language translation and so on, you can add as many languages as you like, no limitation!

**Note:** To change form text put form name in both field tag and id

**Syntax:** 

`Function TranslateForm(ByRef dm_Form As System.Windows.Forms.Form, ByVal dm_Language As Byte)`

**Example:** 

`DM.TranslateForm(Me, 3)`

This will populate your form text and all its labels with your translation in the field "Languge3" in the table "Multilanguage"

# FlipForm

We support Eastern languages Arabic, Chinese, and so on. So we support right to left alignment and orientation, we rotate form horizontally 180

**Syntax:**

`Function FlipForm(ByRef dm_Form As System.Windows.Forms.Form)`

**Example:**

```
DM.FlipForm(Me) 

DM.TranslateForm(Me, 2)

DM.Rifgt2Left(True)
```

This will load the Arabic language which is located in field language 2, and flip the form horizontally and align text from right to left.

# Right2Left

We support Eastern languages so we align all your text right if you want.

**Syntax:** 

`Function Right2Left(ByVal Mode As Boolean)`

**Example:** 

`DM.Right2Left(True)`

# EnableReturnKey

Enable you to navigate through controls with the Return key as with the tab key.

**Syntax:**

`Function EnableReturnKey(ByVal Mode As Boolean)`

**Example:**

`DM.EnableReturnKey(True)`

# Configuration Utility 

We supply you with Configuration Utility which enables you to assign your own language used with DC.DataManger

# Tutorial

This tutorial describes most of the features supported by DC.DataManger. Also, you can refer to the project example which is installed by default into C:\Program Files\Dynamic Components\Data Manger\Tutorial\

```vb
Dim DM As New DynamicComponents.DataManger()

Dim aImage(26) As String  

Dim CN As New ADODB.Connection()

Dim oMaster As New ADODB.Recordset()

Dim oDetails As New ADODB.Recordset()



Private Sub TestForm_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

  PopulateaImage()
  
  CN.Open("DSN=Me")
  
  oMaster.Open("Orders", CN, oMaster.CursorType.adOpenKeyset, oMaster.LockType.adLockOptimistic)
  
  oDetails.Open("OrderDetails", CN, oDetails.CursorType.adOpenKeyset, oDetails.LockType.adLockOptimistic)

  DM.InitForm(CN, Me, oMaster, AxDataGrid1, oDetails)

  DM.PrepareImageButtons(aImage, "F:\DataManage-ADO\icons\", False)

  DM.NavigationButtons("FirstButton", "PrevButton", "NextButton", "LastButton")

  DM.ManipulationButtons("OkButton", "NewButton", "DeleteButton", "ExitButton", "SearchButton")

  DM.KeyFields("OrderId")

  DM.SetLink("OrderId", "OrderId")

  AxDataGrid1.DataSource = oDetails

  DM.AddRelatedValue("Customers", "CustomerID", "CustomerID", "CustomerName", "xCustomerName", 3)

  DM.AddRelatedValue("Shippers", "ShipperId", "ShipVia", "CompanyName", "xCompanyName", 2)

  DM.AddGridRelatedValue("Products", "ProductID", "ProductID", "ProductName", "ProductName", 2)

  DM.KeyLeaveField(oMaster, "OrderId", 5)

  DM.RequiredFields("OrderId+OrderDate+CustomerId")

  DM.NumericFields("CustomerID", "OrderId", "ShipVia")

  DM.DecimalFields("Freight")

  DM.DateFields("OrderDate")

  DM.DecimalPlaces(2)

  DM.EnableReturnKey(True)

  DM.Right2Left(True)

  DM.FlipForm(Me)

  DM.TranslateForm(Me, 1)

  DM.PopulateForm(Me, oMaster, AxDataGrid1, oDetails)
  
End Sub

Private Sub PopulateaImage()

  aImage(0) = "First.ico"
  
  aImage(1) = "FirstOver.ico"
  
  aImage(2) = "FirstDown.ico"
  
  aImage(3) = "Previous.ico"
  
  aImage(4) = "PreviousOver.ico"
  
  aImage(5) = "PreviousDown.ico"
  
  aImage(6) = "Next.ico"
  
  aImage(7) = "NextOver.ico"
  
  aImage(8) = "NextDown.ico"
  
  aImage(9) = "Last.ico"
  
  aImage(10) = "LastOver.ico"
  
  aImage(11) = "LastDown.ico"
  
  aImage(12) = "Ok.ico"
  
  aImage(13) = "OkOver.ico"
  
  aImage(14) = "OkDown.ico"
  
  aImage(15) = "New.ico"
  
  aImage(16) = "NewOver.ico"
  
  aImage(17) = "NewDown.ico"
  
  aImage(18) = "Delete.ico"
  
  aImage(19) = "DeleteOver.ico"
  
  aImage(20) = "DeleteDown.ico"
  
  aImage(21) = "Exit.ico"
  
  aImage(22) = "ExitOver.ico"
  
  aImage(23) = "ExitDown.ico"
  
  aImage(24) = "Search.ico"
  
  aImage(25) = "SearchOver.ico"
  
  aImage(26) = "SearchDown.ico"
  
End Sub
```
