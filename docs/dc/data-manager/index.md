DC Data Manger
=================

Overview
---------

DC.DataManger is a high-performance COM-based environments such as Visual Basic, Visual C++ , it is only 80 KB DLL , so enjoy speed performance.

DC.DataManger class has all the magic ,imaginary and incredible features you can find any where in the market.

DC.DataManger is an enhanced class that handles all aspects required with a data form (including single form and master-details form).

DC.DataManger class handles all the events required that you rarely need few lines of additional programming code.

DC.DataManger class is the best decision for software companieswhich needs programming on no time or companies depends on novice programmers . 

EgyFirst has done a lot of work for you. You define few methods and properties of DC.DataManger classand wedo the rest.

# **Features**
Few Lines to add in your Form\_Load event and you will get full control over your form and all included (TextBox - Lables-Buttons-Grid-Recordset) and all related events (Leave-paint-Keypress-AfterColEdit-OnAddNew-Click-MouseEnter-MouseLeave-MouseDown-Enter)

**You can:**

- Navigate first ,previous , next and last 
- Add new records ,edit it ,save it , or delete it 
- Retrieve related names to your fields code 
- Trigger sensitive DataHelp to select fromby pressing F1 
- Trigger sensitive Help by pressing F12 
- Validate your entry by restrict it to predefined type(Numeric-Alphabetic-AlphaNumeric-Date-Decimal) or to your defined characters 
- Notify you with red forecolor if your entry is not proper 
- Format data by define decimal places for numeric entry , or define letter case for charactes entry 
- Change button image according to mouse movement or focus change 
- Support MultiLanguage Application , by populate form labels with predefined translation automatically 
- Support Eastern Language , we support right to left application by changing alignment to right and orientation by flip form horizontally 180 
- Enable you navigate through controls with Return key as with tab key

**Example:**

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

after this few lines you will get full automated controling on your form without any additional code to write , it is incredible !


# **Convention**

There are Two Rules you must know about DC.DataManger

1. Textbox Controls which located in your data form must have the same names as their Fields names in related table and Columns Controls which involved in your datagrid must have the same names as their Fields names in related table for details
1. Textbox Controls which located in your data form and not have related Field in related table must begin with "x" or "X" character , you can not name related Textbox Control with "X" or "x" prefix




# **System Requirements**
DC.DataMangerruns as a COM class for Developing with Visual Basic.Net underMicrosoft Windows 98/NT/ 2000 or Windows XP. 
# **Installing DC.DataManger**
The DC.DataManger setup program will automatically register theDC\_DataManger10.dll file on your system. 

There is no need to manually run RegSvr32.exe on your development system. 
# **Including DC.DataManger**

To include DC.DataManger in your project 

1. From Project menu select add reference 
1. Push Browse button to locate your DC\_DataManger10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32) , now the specific DLL included in your references
1. Be sure that Micorsoft DataGrid Control Vresion 6.0 (OLEDB) is included in your Toolbox , if not then right click Toolbox 
1. From shortcut menu select customize Toolbox
1. From customize Toolbox Dialog ,scroll down and check Micorsoft DataGrid Control Version 6.0 (OLEDB)


# **Deploying DC.DataManger Applications**
The only file needs to be distributed withDC.DatManger COM applications is DC\_DataManger10.dll

this file should be copied to the WinSystem directory which by default is C:\Windows\System32 

**Note :** 

If you deploy a translated application with your local language , you must deploy DCDM10\_Lang.dll which located in your system directory which is by default [C:\Windows\System32\](file:///C:/Windows/System32/) and place it in end user system directory
## **How to Create a DSN** 

1- Open Windows’ ODBC Data Source Administrator as follows:
In Windows 95, 98, or NT, choose Start > Settings > Control Panel, then double-click the ODBC Data 
Sources icon. Depending on your system, the icon could also be called ODBC or32bit ODBC.
in Windows 2000, choose Start > Settings > Control Panel > Administrative Tools > DataSources.
In Windows XP, choose Start > Control Panel > Performance and Maintenance > Administrative Tools > 
Data Sources (ODBC).


2- Click the SystemDSNtab.
The tab displays the list of DSNs currently on your system. 

3- Click Add to add a new DSN to the list.
The Create New Data Source dialog box appears, listing all the drivers currently loaded on your system. 

4- Select a driver from the list, then click Finish

**Example:**

If your database is a Microsoft Access file, select Microsoft Access Driver (\*.mdb). If a driver for your product does not appear in the list, you’llhave to download the driver from a vendor’s website and install it. 

In the dialog box that appears, enter a name for the DSN and specify the connection parameters.

The dialog boxes for specifying parameters differ depending on the driver you selected. For the Microsoft Access Driver, you enter a name, click Select, locate the database file on the hard disk, and click OK. 

Click OK to close the dialog box.

The new DSN is added to your list of system DSNs. 


# **InitForm**
# 
Prepare form to know every thing about the form and its controls and all binding data . so it must be the first assignment in your code . an errors may occurs if you do not
# **syntax:**
Function InitForm(ByRef dm\_DSN As ADODB.Connection, ByRef dm\_Form As System.Windows.Forms.Form, ByRef dm\_MasterTable As ADODB.Recordset, Optional ByRef dm\_Grid As AxMSDataGridLib.AxDataGrid = Nothing, Optional ByRef dm\_DetailTable As ADODB.Recordset = Nothing)

dm\_DSN is a reference to your DSN connection

dm\_Form is a reference to your form which passed as 'Me' keyword

dm\_MasterTable is a reference to your Master Recordset

Optional dm\_Grid (if your form has a grid) is a reference to your grid

Optional dm\_DetailTable (if your form has a grid) is a reference to your Details Recordset

**Example:**

Dim oMaster As New ADODB.Recordset()

Dim oDetails As New ADODB.Recordset()

Dim DM As New DataManger()

Private Sub TestForm\_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

CN.Open("DSN=NorthWind")

oMaster.Open("Orders", CN, oMaster.CursorType.adOpenKeyset, oMaster.LockType.adLockOptimistic)

oDetails.Open("OrderDetails", CN, oDetails.CursorType.adOpenKeyset, oDetails.LockType.adLockOptimistic)

DM.InitForm(CN, Me, oMaster, AxDataGrid1, oDetails)

End Sub
# **KeyFields**
# 
it assigns the fields in your Recordset which not allowed to duplicate

**Syntax:**

Function KeyFields(ByVal str\_KeyFields As String)

**Note:**

multi fields can concatenated by plus sign '+'

**Example:**

DM.KeyFields("Flag+OrderId")
# **KeyLeaveField**

it assigns the fields in your Recordset which will retieve new data when focus chang away from it

**Syntax:**

Function KeyLeaveField(ByRef dm\_MasterTable As ADODB.Recordset, ByVal str\_KeyLeaveField As String, Optional ByVal n\_ZeroPad As Byte = 0)

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.002.png)

**Note:**

n\_ZeroPad parameter padding data with "0" character

this mean that '34' with n\_ZeroPad is 4 will be '0034' 

this is useful for indexing and searching purposes if you want , remember that is an optional parameter

**Example:**

DM.KeyLeaveField(oMaster, "OrderId", 5)
# **SetLink**
It assigns the fields in your Master Recordset which are linked to related fields inDetails Recordset

**Syntax:**

Function Sub SetLink(ByVal str\_MasterFields As String, ByVal str\_DetailFields As String)

**Note:**

**multi fields can concatenated by plus sign '+'**

**Example:**

DM.SetLink("Flag+OrderId", "Flag+OrderId")


# **AddRelatedValue**
Retrieve the related value to your field code 

assume you save Cust\_Code in your master recordset 

when you retrieve data you also want to get Cust\_Name form Customers table . AddRelatedValue Function do that for you easily

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.002.png)

**Syntax:**

Function AddRelatedValue(ByRef str\_Table As String, ByVal str\_Key As String, ByVal str\_Control As String, ByVal str\_RetValue As String, ByVal str\_RetControl As String, Optional ByVal n\_ZeroPad As Byte = 0)

**Note:**

n\_ZeroPad parameter padding data with "0" character

this mean that '34' with n\_ZeroPad is 4 will be '0034' 

this is useful for indexing and searching purposes if you want , remember that is an optional parameter

**Example:**

DM.AddRelatedValue("Customers", "CustomerID", "CustomerID", "CustomerName", "xCustomerName", 3)




# **AddGridRelatedValue**
It retrieve the related value to your grid field code

assume you save Productt\_Code in your Detail recordset

when you retrieve data you also want to get Product\_Name form Products table . AddRelatedValue Function do that for you easily

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.002.png)

**Syntax:**

Function AddGridRelatedValue(ByVal str\_Table As String, ByVal str\_TableKey As String, ByVal str\_Column As String, ByVal str\_TableRetField As String, ByVal str\_GridRetColumn As String, ByVal n\_ZeroPad As Byte)

**Note:**

n\_ZeroPad parameter padding data with "0" character

this mean that '34' with n\_ZeroPad is 4 will be '0034' 

this is useful for indexing and searching purposes if you want , remember that is an optional parameter

**Example:**

DM.AddGridRelatedValue("Products", "ProductID", "ProductID", "ProductName", "ProductName", 2)
# **FlagField**

Sometimes you use table which involve multi tables within , as "Personal" table which can involve "Customers", "Suppliers" , "Debits" , "Credits" with different flag key 

you can assign value "1" for Customers , assign value "2" for Suppliers and so on

the rest of fields is the same.

We support Tables with Flag field 

**Syntax:**

Function FlagField(ByVal str\_MasterFlagField As String, ByVal str\_DetailFlagField As String, ByVal str\_FlagValue As String)

**Example:**

DM.FlafField("Flag","Flag","2")



# **How to select some fields**

Sometimes you want to include some fields of your detail table , not all its fields
the next example do that 

**Example:**

oDetails.Open("select flag , billno , custno , custname , price from OrderDetails", CN, oDetails.CursorType.adOpenKeyset, oDetails.LockType.adLockOptimistic)

**That is all !**


# **Search**

Easily to search your recordset , add button in your form and notify [Manipulation Buttons ](#chmtopic34)Function with its name

1. Begin search by clicking search button , all form controls will be empty , now you get in Search Mode
1. Enter your pattern to search and click search button again , now your form has the search result
1. Navigate through records which apply your search pattern by[Navigation Buttons](#chmtopic34)
1. Return to Normal Mode by click search button twice

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.002.png)
# **PopulateForm**
it populate your form and its grid with data

it recomnded to be last assignment in your Form\_Load event 

**Syntax:**

Function PopulateForm(ByRef dm\_Form As System.Windows.Forms.Form, ByRef dm\_MasterTable As ADODB.Recordset, Optional ByRef dm\_Grid As AxMSDataGridLib.AxDataGrid = Nothing, Optional ByRef dm\_DetailTable As ADODB.Recordset = Nothing)

**Example:**

DM.PopulateForm(Me, oMaster, AxDataGrid1, oDetails)
# **NumericFields**
It restrict data entry to only valid entry 

valid entry may be one or more of allowed character which is"0123456789" 

**Syntax:** 

Function NumericFields(ByVal ParamArray str\_NumericFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.NumericFields("CustomerID", "OrderId", "ShipVia")
# **AlphabeticFields**
It restrict data entry to only valid entry 

valid entry may be one or more of allowed character which is"abcdefghijklmnopqrstuvwxyz" additional to upper case "ABCDEFGHIJKLMNOPQRSTUVWXYZ" 

**Syntax:** 

Function AlphabeticFields(ByVal ParamArray str\_NumericFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.NumericFields("FirstName", "FamilyName")
# **AlphaNumericFields**
It restrict data entry to only valid entry 

valid entry may be one or more of allowed character which is"abcdefghijklmnopqrstuvwxyz" and upper case "ABCDEFGHIJKLMNOPQRSTUVWXYZ" 

additional to numeric characters "0123456789"

**Syntax:**

Function AlphaNumericFields(ByVal ParamArray str\_NumericFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.NumericFields("Address")
# **DateFields**
It restrict data entry to only valid entry 

valid entry may be one or more of allowed character which is"0123456789" additional to "/-\" characters

when you leave the edited Textbox if data entry is not a date you will be notify by changing forecolor to red color until you reedit it correctly

suppose you enter date like "30/2/2004" 

this is an invalid entry , so you will notify by changing forecolor to red 

**Syntax:**

FunctionDateFields(ByVal ParamArray str\_DateFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.DateFields("OrderDate")
# **DecimalFields**
It restrict data entry to only valid entry 

valid entry may be one or more of allowed character which is"0123456789" additional to decimal point '.'

data entry will be formated by n decimal places defined in [DecimalPlaces](#chmtopic30) Function

when you leave the edited Textbox if data entry is not a date you will be notify by changing forecolor to red color until you reedit it correctly

suppose you enter date like "705.3.2" 

this is an invalid entry , so you will notify by changing forecolor to red 

**Syntax:**

Function DecimalFields(ByVal ParamArray str\_NumericFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.DecimalFields("Freight")
# **SpecialChars**
It restrict data entry to only valid entry 

valid entry may be one or more of charcters which is contained in its parameter

**Syntax:**

Function SpecialChars(ByVal str\_Chars As String)

**Example:**

DM.SpecialChars ("YyNn")
# **SpecialCharsFields**
It restrict data entry to only valid entry 

valid entry may be one or more of charcters which is contained in [SpecialChars](#chmtopic25) function 

**Syntax:** 

Function SpecialCharsFields(ByVal ParamArray 

str\_SpecialFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.SpecialCharsFields ("Married")
# **RequiredFields**
it assigns the fields in your Recordset which can not be empty

**Syntax:**

Function RequiredFields(ByVal str\_RequiredFields As String)

**Note:**

multi fields can concatenated by plus sign '+'

**Example:**

DM.RequiredFields("OrderId+OrderDate+CustomerId")
# **LowerCaseFields**
It converts all characters to lower case

**Syntax:**

Function LowerCaseFields(ByVal ParamArray str\_LowerCaseFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.LowerCaseFields ("SupplierName")
# **UpperCaseFields**
It converts all characters to upper case

**Syntax:**

Function UpperCaseFields(ByVal ParamArray str\_UpperCaseFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.UpperCaseFields ("ProductName")
# **DecimalPlaces**
it formats number by making it in decimal state with n places which you define in your function

**Syntax:**

FunctionDecimalPlaces(ByVal n\_DecimalPlaces As Byte)

**Example:**

DM.DecimalPlaces(2)
# **FirstCharOnlyFields**
It converts only First character to upper case

**Syntax:**

FunctionFirstCharOnlyFields(ByVal ParamArray str\_FirstCharOnlyFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.FirstCharOnlyFields ("CustomerName")
# **FirstCharOfWordsFields**
It converts First character of every words to upper case

**Syntax:**

Function FirstCharOfWordsFields(ByVal ParamArray str\_FirstCharOfWordsFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.FirstCharOfWordsFields("CustomerName")
# **PrepareImageButtons**
Your Data Form have [Navigation](#chmtopic34) & [Manipulation](#chmtopic35) Buttons 

you can assign changeable icons for each button , additionally ,you can assign a motion for each button if you put third parameter to true ,all you need is

- Buttons without Motion

![](file:///D:/Documents%20and%20Settings/MyAccount/My%20Documents/ImageButtons.gif) 

- Buttons with Motion

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.003.png)

1. Declare an array with 27 element 
1. Assign 3 icons for each button 

First icon for MouseLeave state 

second icon for MoveOver state

third icon for MoveDown state

3. Populate your array respectivly with icons as this sequence

FirstButton\_MouseLeave , FirstButton\_MouseOver, FirstButton\_MouseDown

PreviousButton\_MouseLeave , PreviousButton\_MouseOver, PreviousButton\_MouseDown

NextButton\_MouseLeave , NextButton\_MouseOver, NextButton\_MouseDown

LastButton\_MouseLeave , LastButton\_MouseOver, LastButton\_MouseDown

SavedataButton\_MouseLeave , SavedataButton\_MouseOver, SavedataButton\_MouseDown

NewdataButton\_MouseLeave , NewdataButton\_MouseOver, NewdataButton\_MouseDown

DeleteDataButton\_MouseLeave , DeleteDataButton\_MouseOver, DeleteDataButton\_MouseDown

CloseFormButton\_MouseLeave , CloseFormButton\_MouseOver, CloseFormButton\_MouseDown

and optionally you can add SearchButton\_MouseLeave , SearchButton\_MouseOver, SearchButton\_MouseDown

**Syntax:**

Function PrepareImageButtons(ByVal ImagesArray() As String, ByVal ImageFullPath As String, ByVal Motion As Boolean)

**Example:**

DM.PrepareImageButtons(aImage, "C:\MyApp\Icons\", True)

where aImage is your array hold icons

third parameter idicate that you wih to show motion with each button


# **NavigationButtons**
Assign Navigation Buttons names so that DC DataManger do all required with it

**Note:**

Navigation Buttons are Buttons which enable you navigate through recordset by moving it first , previous . next and last.

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.004.png)

**Syntax:**

Public Sub NavigationButtons(ByVal dm\_First As String, ByVal dm\_Previous As String, ByVal dm\_Next As String, ByVal dm\_Last As String)

**Example:**

DM.NavigationButtons("FirstButton", "PrevButton", "NextButton", "LastButton")
# **ManipulationButtons**
Assign Manipulation Buttons names so that DC DataManger do all required with it

**Note:**

Manipulation Buttons are Buttons which enable you add , edit , save or delete records in your recordset .

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.002.png)

**Syntax:**

Function ManipulationButtons(ByVal dm\_Save As String, ByVal dm\_New As String, ByVal dm\_Delete As String, ByVal dm\_Close As String, Optional ByVal dm\_Search As String = Nothing)

**Example:**

DM.ManipulationButtons("OkButton", "NewButton", "DeleteButton", "ExitButton", "SearchButton")
# **Sensitive F1 DataHelp**
When you [AddRelatedValue](#chmtopic14)and your focus is located in the control defined in str\_Control (which is control came)parameter you get 2 magic advantages.

1. When you leave from this control you will retrieve respected value related to this control value 
1. When you press F1 Key this will trigger DataHelp Browser filled with the table defined in str\_Table parameter , you can select any row by double click it , this will close DataHelp Browser and assigned the data selected to the control defined in str\_RetControl parameter

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.002.png)

When you [AddGridRelatedValue](#chmtopic15)and your focus is located in the column defined in str\_Column (which is Column name)parameter you get 2 magic advantages.

1. When you leave from this control you will retrieve respected value related to this control value
1. When you press F1 Key this will trigger DataHelp Browser filled with the table defined in str\_Table parameter , you can select any row by double click it , this will close DataHelp Browser and assigned the data selected to the column defined in str\_GridRetColumn parameter


# **Sensitive F12 Help**
When you press F12 Key , this trigger a sensitive help ,this require

1. Create a new table , name it "Help" and put it in your database 
1. create 4 fields as specified

|Name|Type|Length|
| :- | :- | :- |
|Tag|Text|50|
|Id|Text|50|
|Description|Text|50|
|Contents|Memo||

3. Fill Tag field with your [Form Tag](JavaScript:popup.TextPopup\(popuptxt1,popupfont1,9,9,-1,-1\))

4. Fill Id Field with your control name 

5. Fill Id Field with DataGrid name followed with underscore character "\_" , which will be something like this 

"axDatagrid\_ProductId"

6. Fill Description field with your control Description

7. Fill Contents field with your supported help for this control

**Note:**

To change your form text put form name in both field tag and id

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.005.png)


# **TranslateForm**

We support Multi Language Applications , you can use same application with different languages

All you need is:

1. Create a new table , name it "Multilanguage" and put it in your database 
1. create 4 fields as specified

|Name|Type|Length|
| :- | :- | :- |
|Tag|Text|50|
|Id|Text|50|
|Language1|Text|50|
|Language2|Text|50|

3. Fill Tag field with your Form Name

4. Fill Id Field with your Label name

5. Fill Language1 field with your first language translation

6. Fill Language2 field with your second language translation and so on , you can add many 
languages as you like , no limitation !

**Note:**

to change form text put form name in both field tag and id

**Syntax:**

Function TranslateForm(ByRef dm\_Form As System.Windows.Forms.Form, ByVal dm\_Language As Byte)

**Example:**

DM.TranslateForm(Me, 3)

This will populate your form text and all its labels with your translation in field "Languge3" in table "Multilanguage"

Example of French Translation

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.002.png)




# **FlipForm**

We support eastern languages Arabic , Chinese and so on 

so we support right to left alignment and orientation , we rotate form horizontally 180

**Syntax:**

Function FlipForm(ByRef dm\_Form As System.Windows.Forms.Form)

**Example:**

DM.FlipForm(Me)

DM.TranslateForm(Me, 2)

DM.Rifgt2Left(True)

this will load Arabic language which located in field language2 and flip form horizontally and align text right to left

what amazing !

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.006.png)


# **Right2Left**

we support eastern languages so we align all your text right if you want

**Syntax:**

Function Right2Left(ByVal Mode As Boolean)

**Example:**

DM.Right2Left(True)

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.007.png)




# **EnableReturnKey**
Enable you navigate through controls with Return key as with tab key

**Syntax:**

Function EnableReturnKey(ByVal Mode As Boolean)

**Example:**

DM.EnableReturnKey(True)
# **Configuration Utility**

We supply you with Configuration Utility which enable you to assign your own language used with DC.DataManger 

![](images/Aspose.Words.fb769b29-ee01-46e2-9d7b-c0f6031e42e7.008.png)




# Tutorial

This tutorial describe most of features supported by DC.DataManger

also you can refer to the project example which installed by default into C:\Program Files\Dynamic Components\Data Manger\Tutorial\


```vb
Dim DM As New DynamicComponents.DataManger()

Dim aImage(26) As String

Dim CN As New ADODB.Connection()

Dim oMaster As New ADODB.Recordset()

Dim oDetails As New ADODB.Recordset()



Private Sub TestForm\_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

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
