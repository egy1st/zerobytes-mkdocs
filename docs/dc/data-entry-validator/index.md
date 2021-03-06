DC DataEntry Validator
===========================


Overview
---------

DC.DataEntryValidator is a COM based component that allows you to Validate your data entry and restrict it to predefined type(Numeric-Alphabetic-AlphaNumeric-Date-Decimal) or to your defined

DC.DataEntryValidator may be used with any developing language support COM based application like Visual Basic,Visual C++,Borland C++,Delphi and others ..

DC.DataEntryValidator will Notify you with red forecolor when your entry is not proper , so there is some thing wrong with data entry in that Textbox

DC.DataEntryValidator will Format data by define decimal places for numeric entry , or define letter case for charactes entry 

EgyFirst has done a lot of work for you. You define few lines of code and we validate and format data entry for you
## **Features**
Few Lines to add in your Form\_Load event and you will get full control over your data entry by Validate it and format it 

**You can:**

- Validate your data entry by restrict it to predefined type(Numeric-Alphabetic-AlphaNumeric-Date-Decimal) or to your defined characters 
- Notify you with red forecolor if your entry is not proper 
- Format numbers by define decimal places for numeric entry 
- Format string by define letter case for charactes entry (Lower Case , Upper Case , Only First Character is Capital )

**Note:**

alphabetic characters may be any character with in (abcdefghijklmnopqrstuvwzyzABCDEFGHIJKLMNOPQRSTUVWXYZ) 

numeric characters may be any character with in (0123456789)

AlphaNumericFields must be numeric or alphabetic characters (0123456789abcdefghijklmnopqrstuvwzyzABCDEFGHIJKLMNOPQRSTUVWXYZ) 

DateFields must be accepted date like (13/12/1971) if your data is wrong we will notify you with red forecolor

**Example:**

DV.InitForm(Me) 

DV.[NumericFields](##chmtopic9)("CustomerId") 
DV.[AlphabeticFields](##chmtopic10)("CustomerName")
DV.[FirstCharOfWordsFields](##chmtopic19)("CustomerName")
DV.[AlphaNumericFields](##chmtopic11)("Address")
DV.[FirstCharOnlyFields](##chmtopic19)("Address")
DV.[NumericFields](##chmtopic9)("phone")
DV.[DecimalFields](##chmtopic13)("MaxDebit")
DV.[DecimalPlaces](##chmtopic18)(2)
DV.[DateFields](##chmtopic12)("LastDeal")



## **System Requirements**
DC.DataEntryValidatorruns as a COM class for Developing with Visual Basic.Net underMicrosoft Windows 98/NT/ 2000 or Windows XP. 


## **Installing DC.DataEntryValidator**
The DC.DataEntryValidator setup program will automatically register theDC\_DataEntryValidator10.dll file on your system. 

There is no need to manually run RegSvr32.exe on your development system. 
## **Including DC.DataEntryValidator**

To include DC.DataEntryValidator in your project 

1. From Project menu select add reference 
1. Push Browse button to locate your DC\_DataEntryValidator10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32) , now the specific DLL included in your references


## **Deploying DC.DataEntryValidator Applications**
The only file needs to be distributed withDC.DataEntryValidator COM applications is DC\_DataEntryValidator10.dll

this file should be copied to the WinSystem directory which by default is C:\Windows\System32 
## **InitForm**

Prepare form to know every thing about the form and its controls . so it must be the first assignment in your code . an errors may occurs if you do not
## **syntax:**
Function InitForm(ByRef dm\_Form As System.Windows.Forms.Form)

dm\_Form is a reference to your form which passed as 'Me' keyword

**Example:**

Dim DV As New DynamicComponents.DataEntryValidator()
DV.InitForm( Me)


## **NumericFields**
It restrict data entry to only valid entry 

valid entry may be one or more of allowed character which is"0123456789" 

**Syntax:**

Function NumericFields(ByVal ParamArray str\_NumericFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DV.NumericFields("CustomerID", "OrderId", "ShipVia")
## **AlphabeticFields**
It restrict data entry to only valid entry 

valid entry may be one or more of allowed character which is"abcdefghijklmnopqrstuvwxyz" additional to upper case "ABCDEFGHIJKLMNOPQRSTUVWXYZ" 

**Syntax:** 

Function AlphabeticFields(ByVal ParamArray str\_NumericFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.NumericFields("FirstName", "FamilyName")
## **AlphaNumericFields**
It restrict data entry to only valid entry 

valid entry may be one or more of allowed character which is"abcdefghijklmnopqrstuvwxyz" and upper case "ABCDEFGHIJKLMNOPQRSTUVWXYZ" 

additional to numeric characters "0123456789"

**Syntax:**

Function AlphaNumericFields(ByVal ParamArray str\_NumericFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.NumericFields("Address")
## **DateFields**
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

DV.DateFields("OrderDate")
## **DecimalFields**
It restrict data entry to only valid entry 

valid entry may be one or more of allowed character which is"0123456789" additional to decimal point '.'

data entry will be formated by n decimal places defined in [DecimalPlaces](##chmtopic18) Function

when you leave the edited Textbox if data entry is not a date you will be notify by changing forecolor to red color until you reedit it correctly

suppose you enter date like "705.3.2" 

this is an invalid entry , so you will notify by changing forecolor to red 

**Syntax:**

Function DecimalFields(ByVal ParamArray str\_NumericFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DV.DecimalFields("Freight")
## **SpecialChars**
It restrict data entry to only valid entry 

valid entry may be one or more of charcters which is contained in its parameter

**Syntax:**

Function SpecialChars(ByVal str\_Chars As String)

**Example:**

DV.SpecialChars ("YyNn")
## **SpecialCharsFields**
It restrict data entry to only valid entry 

valid entry may be one or more of charcters which is contained in [SpecialChars](##chmtopic14) function 

**Syntax:** 

Function SpecialCharsFields(ByVal ParamArray 

str\_SpecialFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DV.SpecialCharsFields ("Married")
## **LowerCaseFields**
It converts all characters to lower case

**Syntax:**

Function LowerCaseFields(ByVal ParamArray str\_LowerCaseFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DM.LowerCaseFields ("SupplierName")
## **UpperCaseFields**
It converts all characters to upper case

**Syntax:**

Function UpperCaseFields(ByVal ParamArray str\_UpperCaseFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DV.UpperCaseFields ("ProductName")
## **DecimalPlaces**
it formats number by making it in decimal state with n places which you define in your function

**Syntax:**

FunctionDecimalPlaces(ByVal n\_DecimalPlaces As Byte)

**Example:**

DV.DecimalPlaces(2)
## **FirstCharOnlyFields**
It converts only First character to upper case

**Syntax:**

FunctionFirstCharOnlyFields(ByVal ParamArray str\_FirstCharOnlyFields() As String)

**Note:**

multi fields can concatenated by comma ","

**Example:**

DV.FirstCharOnlyFields ("CustomerName")
## Tutorial

This tutorial describe most of features supported by DC.DataEntryValidator

also you can refer to the project example which installed by default into C:\Program Files\Dynamic Components\DataEntryValidator\Tutorial\


``` vb
Dim DV As New DynamicComponents.DataEntryValidator()

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

DV.InitForm(Me) 
//must be your first assignment , an error occurs if not

DV.NumericFields("CustomerId") 
//CustomerId must be numeric characters(0123456789)

DV.AlphabeticFields("CustomerName")
//CustomerName must be alphabetic characters (abcdefghijklmnopqrstuvwzyzABCDEFGHIJKLMNOPQRSTUVWXYZ) 

DV.FirstCharOfWordsFields("CustomerName")
//'First charecter of every word will be in uooer case

DV.AlphaNumericFields("Address")
//'Address must be numeric or alphabetic characters (0123456789abcdefghijklmnopqrstuvwzyzABCDEFGHIJKLMNOPQRSTUVWXYZ) 

DV.FirstCharOnlyFields("Address")
//'First charecter of first word only will be in uooer case 

DV.NumericFields("phone")
//'Phone must be numeric characters(0123456789)

DV.DecimalFields("MaxDebit")
//'MaxDebit must be decimal characters(0123456789 & .) 

DV.DecimalPlaces(2)
//'MaxDebit will be formatted with 2 decimal digits

DV.DateFields("LastDeal")
//'LastDeal must be accepted date(0123456789-\/)

End Sub
```
