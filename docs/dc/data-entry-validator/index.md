# DC DataEntry Validator

## Overview

DC.DataEntryValidator is a COM based component that allows you to validate your data entry and restrict it to predefined types (Numeric, Alphabetic, AlphaNumeric, Date, Decimal) or your own defined types.

DC.DataEntryValidator may be used with any developing language that supports COM based applications like Visual Basic, Visual C++, Borland C++, Delphi and others.

DC.DataEntryValidator will notify you with red forecolor when your entry is not proper, so there is something wrong with the data entry in that textbox.

DC.DataEntryValidator will format data by defining decimal places for numeric entry, or defining letter case for character entry.

EgyFirst has done a lot of work for you. You define a few lines of code and we validate and format data entry for you.

## **Features**

A few lines in your Form_Load event gives you full control over your data entry by validating it and formatting it.

**You can:**

- Validate your data entry by restricting it to predefined types (Numeric, Alphabetic, AlphaNumeric, Date, Decimal) or your own defined types.
- Notify with red forecolor if your entry is not proper.  
- Format numbers by defining decimal places for numeric entry.  
- Format strings by defining letter case (Lower Case, Upper Case, Only First Character Capital).

**Note:** 

- Alphabetic characters may be any character within "abcdefghijklmnopqrstuvwxyz" additionally upper case "ABCDEFGHIJKLMNOPQRSTUVWXYZ".

- Numeric characters may be any character within "0123456789".

- AlphaNumericFields must be numeric or alphabetic characters "0123456789abcdefghijklmnopqrstuvwzyzABCDEFGHIJKLMNOPQRSTUVWXYZ".

- DateFields must be accepted date formats like "13/12/1971". If your data is wrong we will notify you with red forecolor.

**Example:**

```vb
DV.InitForm(Me) 

DV.NumericFields("CustomerId")
DV.AlphabeticFields("CustomerName") 
DV.FirstCharOfWordsFields("CustomerName")
DV.AlphaNumericFields("Address")
DV.FirstCharOnlyFields("Address")
DV.NumericFields("phone")
DV.DecimalFields("MaxDebit")
DV.DecimalPlaces(2)  
DV.DateFields("LastDeal")
```

## **System Requirements**

DC.DataEntryValidator runs as a COM class for developing with Visual Basic.NET under Microsoft Windows 98/NT/2000 or Windows XP.


## **Installing DC.DataEntryValidator**

The DC.DataEntryValidator setup program will automatically register the DC_DataEntryValidator10.dll file on your system.

There is no need to manually run RegSvr32.exe on your development system.

## **Including DC.DataEntryValidator** 

To include DC.DataEntryValidator in your project:

1. From Project menu select Add Reference.
2. Click Browse button to locate your DC_DataEntryValidator10.DLL file which by default is located in [c:\windows\system32](file:///c:/windows/system32). Now the specific DLL is included in your references.


## **Deploying DC.DataEntryValidator Applications**

The only file that needs to be distributed with DC.DataEntryValidator COM applications is DC_DataEntryValidator10.dll. 

This file should be copied to the WinSystem directory which by default is C:\Windows\System32.

## **InitForm**

Prepares the form to know everything about the form and its controls. So it must be the first assignment in your code or errors may occur if you do not call it first.

**Syntax:**

```vb
Function InitForm(ByRef dm_Form As System.Windows.Forms.Form)
```

dm_Form is a reference to your form which is passed as the 'Me' keyword. 

**Example:** 

```vb 
Dim DV As New DynamicComponents.DataEntryValidator()
DV.InitForm(Me)
```

## **NumericFields**

Restricts data entry to only valid numeric entries.

Valid entries may be one or more of the allowed characters "0123456789".

**Syntax:**

```vb
Function NumericFields(ByVal ParamArray str_NumericFields() As String) 
```

**Note:**

Multiple fields can be concatenated by comma ",".

**Example:**

```vb
DV.NumericFields("CustomerID", "OrderId", "ShipVia") 
```

## **AlphabeticFields**

Restricts data entry to only valid alphabetic entries.  

Valid entries may be one or more of the allowed characters "abcdefghijklmnopqrstuvwxyz" additionally upper case "ABCDEFGHIJKLMNOPQRSTUVWXYZ".

**Syntax:**

```vb  
Function AlphabeticFields(ByVal ParamArray str_NumericFields() As String)
```

**Note:** 

Multiple fields can be concatenated by comma ",". 

**Example:**

```vb
DM.NumericFields("FirstName", "FamilyName")
```

## **AlphaNumericFields**

Restricts data entry to only valid alphanumeric entries.

Valid entries may be one or more of the allowed characters "abcdefghijklmnopqrstuvwxyz" upper case "ABCDEFGHIJKLMNOPQRSTUVWXYZ" additionally numeric characters "0123456789". 

**Syntax:** 

```vb
Function AlphaNumericFields(ByVal ParamArray str_NumericFields() As String) 
```

**Note:** 

Multiple fields can be concatenated by comma ",".

**Example:** 

```vb 
DM.NumericFields("Address")
```

## **DateFields**

Restricts data entry to only valid date entries.  

Valid entries may be one or more of the allowed characters "0123456789" additionally "/" and "-" characters. 

When you leave the edited textbox, if the data entry is not a valid date you will be notified by changing forecolor to red until you re-edit it correctly.

For example if you enter "30/2/2004" this is an invalid date, so you will be notified by changing forecolor to red.

**Syntax:**

```vb
Function DateFields(ByVal ParamArray str_DateFields() As String)
```

**Note:**

Multiple fields can be concatenated by comma ",".

**Example:**

```vb  
DV.DateFields("OrderDate")
```

## **DecimalFields**

Restricts data entry to only valid decimal entries.   

Valid entries may be one or more of the allowed characters "0123456789" additionally decimal point '.'. 

Data entry will be formatted by n decimal places defined in the [DecimalPlaces](#DecimalPlaces) function.

When you leave the edited textbox, if the data entry is not a valid decimal you will be notified by changing forecolor to red until you re-edit it correctly. 

For example if you enter "705.3.2" this is an invalid decimal, so you will be notified by changing forecolor to red.

**Syntax:** 

```vb
Function DecimalFields(ByVal ParamArray str_NumericFields() As String)
```

**Note:** 

Multiple fields can be concatenated by comma ",".

**Example:**

```vb 
DV.DecimalFields("Freight") 
```

## **SpecialChars**

Restricts data entry to only valid entries containing the defined special characters.

Valid entries may be one or more of characters contained in the parameter string.

**Syntax:**

```vb
Function SpecialChars(ByVal str_Chars As String)
```

**Example:** 

```vb
DV.SpecialChars("YyNn") 
```

## **SpecialCharsFields**

Restricts data entry to only valid entries containing the defined special characters.

Valid entries may be one or more of characters contained in the [SpecialChars](#SpecialChars) function.

**Syntax:**

```vb 
Function SpecialCharsFields(ByVal ParamArray str_SpecialFields() As String)
``` 

**Note:** 

Multiple fields can be concatenated by comma ",". 

**Example:**

```vb
DV.SpecialCharsFields("Married")
```

## **LowerCaseFields** 

Converts all characters to lower case.

**Syntax:** 

```vb
Function LowerCaseFields(ByVal ParamArray str_LowerCaseFields() As String)
```

**Note:**

Multiple fields can be concatenated by comma ",".

**Example:**

```vb 
DM.LowerCaseFields("SupplierName")
```

## **UpperCaseFields**

Converts all characters to upper case. 

**Syntax:**

```vb 
Function UpperCaseFields(ByVal ParamArray str_UpperCaseFields() As String) 
```

**Note:** 

Multiple fields can be concatenated by comma ",".

**Example:** 

```vb
DV.UpperCaseFields("ProductName")
``` 

## **DecimalPlaces** 

Formats numbers by setting the number of decimal places.

**Syntax:** 

```vb
Function DecimalPlaces(ByVal n_DecimalPlaces As Byte)
```

**Example:**

```vb
DV.DecimalPlaces(2)
```

## **FirstCharOnlyFields**

Converts only the first character to upper case.

**Syntax:**

```vb
Function FirstCharOnlyFields(ByVal ParamArray str_FirstCharOnlyFields() As String)
``` 

**Note:**

Multiple fields can be concatenated by comma ",".

**Example:**

```vb  
DV.FirstCharOnlyFields("CustomerName")
```

## Tutorial

This tutorial describes most of the features supported by DC.DataEntryValidator.

You can also refer to the project example which is installed by default into C:\Program Files\Dynamic Components\DataEntryValidator\Tutorial\.


```vb
Dim DV As New DynamicComponents.DataEntryValidator()

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

  DV.InitForm(Me)
  // Must be your first assignment, an error occurs if not

  DV.NumericFields("CustomerId")
  // CustomerId must be numeric characters(0123456789)

  DV.AlphabeticFields("CustomerName")
  // CustomerName must be alphabetic characters (abcdefghijklmnopqrstuvwzyzABCDEFGHIJKLMNOPQRSTUVWXYZ)

  DV.FirstCharOfWordsFields("CustomerName") 
  // First character of every word will be in uppercase

  DV.AlphaNumericFields("Address")
  // Address must be numeric or alphabetic characters (0123456789abcdefghijklmnopqrstuvwzyzABCDEFGHIJKLMNOPQRSTUVWXYZ)

  DV.FirstCharOnlyFields("Address")
  // First character of first word only will be in uppercase

  DV.NumericFields("phone") 
  // Phone must be numeric characters(0123456789)

  DV.DecimalFields("MaxDebit")
  // MaxDebit must be decimal characters(0123456789 & .)

  DV.DecimalPlaces(2)
  // MaxDebit will be formatted with 2 decimal digits

  DV.DateFields("LastDeal")
  // LastDeal must be accepted date(0123456789-\/)

End Sub
```
