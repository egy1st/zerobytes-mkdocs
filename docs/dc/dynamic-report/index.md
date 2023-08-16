# DC Dynamic Report

## System Requirements

DC.DynamicReport runs as a COM class for inclusion in any developing language that supports COM based applications like Visual Basic, Visual C++, Borland C++, Delphi, and others.

## Installing DC.DynamicReport

The DC.DynamicReport setup program will automatically register the DC_DynamicReport10.dll file on your system.  

There is no need to manually run RegSvr32.exe on your development system.

## Including DC.DynamicReport

To include DC.DynamicReport in your project:

1. From the Project menu select Add Reference.
2. Click Browse button to locate your DC_DynamicReport10.DLL file which by default is located in [c:\windows\system32](file:///c:/windows/system32). Now the specific DLL is included in your references.

## Deploying DC.DynamicReport

There are two files that need to be distributed with DC.Num2Text COM based applications:

- DC_DynamicReport10.dll
- DC_DynamicReport_Theme.dat

These files should be copied to the WinSystem directory which by default is C:\Windows\System32.

## InitReport Function

The InitReport Function must be your first assignment, an error may occur if you do not call it first. 

We support Eastern languages in all of our components, so Dynamic Report comes with support for right-to-left orientation.

**Syntax:**

```vb
Public Sub InitReport(ByVal Right2Left As Boolean)
```

It takes 1 parameter:

1. Right2Left defines orientation. If True, this is useful for eastern languages that use the right orientation.


**Example:**

```vb
oRep.InitReport(False) 
```

## ReadTheme Function

The ReadTheme function enables you to select from 7 different themes. By changing the theme you change the whole appearance of the report.

**Syntax:** 

```vb 
Public Sub ReadTheme(ByVal int_ThemeID As Theme_ID)
```

int_ThemeID may take any value from 1 to 6:

- Classic = 1
- Blue = 2 
- Red = 3
- Green = 4
- Simple = 5
- Transparent = 6

**Example:**

```vb
oRep.ReadTheme(DynamicComponents.DynamicReport.Theme_ID.Classic) ' Default theme is Classic
```

## LogoImage Function 

The LogoImage function enables you to set your company logo.

**Syntax:**

```vb
Public Sub LogoImage(ByVal str_LogoFile As String, ByVal str_LogoPath As String)
```

It takes 2 parameters:

1. str_LogoFile is the logo file name. 
2. str_LogoPath is the logo file path.

**Example:**

```vb  
oRep.LogoImage("Logo.bmp", "C:\Images\")
```

## SetTitle Function

The SetTitle function enables you to set the title of the report.

**Syntax:** 

```vb
Public Sub SetTitle(ByVal str_Title As String)
```

**Example:**

```vb
oRep.SetTitle("Customers List") 
```

## SetReportHeader Function

The SetReportHeader function enables you to set report header lines. You can add as many lines as you want.

**Syntax:**

```vb
Public Sub SetReportHeader(ByVal ParamArray str_Line() As String)
```

It takes a parameter array, so you can add as many header lines as you want, delimited by a comma ",".

**Example:**

```vb  
oRep.SetReportHeader("This is Dynamic Report v1.0", "It is powered by EgyFirst Inc..", "Dynamic Components is a trademark since 2004")
```

## GroupBy Function

The GroupBy function enables you to set grouping data. You can add as many grouping fields as you want.

**Syntax:**

```vb
Public Sub GroubBy(ByVal str_GroupField As String, ByVal ShowGroupNavigator As Boolean, ByVal ForceNewPage As Boolean)
```

It takes 3 parameters:

1. str_GroupField parameter is the field used for grouping data.
2. ShowGroupNavigator parameter determines if you want to show a group navigator or not. The group navigator enables you to go directly to a selected group.
3. ForceNewPage parameter, if True, every group will be viewed and printed on a new page.


**Example:** 

```vb
oRep.GroubBy("OrderID", True, True)
```

## SumFields Function

The SumFields function enables you to sum defined fields.

**Syntax:**  

```vb 
Public Sub SumFields(ByRef ReportTable As ADODB.Recordset, ByVal ParamArray str_Line() As String)
```

It takes 2 parameters:

1. ReportTable parameter is a recordset used to populate the report. 
2. str_Line is a parameter array, so you can add as many summed fields as you want, delimited by comma ",".

**Example:**

```vb
Dim oMaster As New ADODB.Recordset()
Dim CN As New ADODB.Connection()

CN.Open("DCDR_NWind")
oMaster.Open("Select * from orders", CN, oMaster.CursorType.adOpenKeyset, oMaster.LockType.adLockOptimistic) 

oRep.SumFields(oMaster, "Quantity", "Value")
```

## SetCaption Function 

The SetCaption function enables you to set captions for fields which may differ from their names. This means a field named "ID" may get a new caption like "Customer ID".

**Syntax:** 

```vb
Public Sub SetCaption(ByVal ParamArray str_Line() As String)
```

It takes a parameter array, so you can add as many captions as you want, delimited by comma ",".

**Example:**

```vb
oRep.SetCaption("Order ID", "Product ID", "Product Name", "Unit Price", "Quantity", "Discount")
```

## SetReportFooter Function

The SetReportFooter function enables you to set report footer lines. You can add as many lines as you want. 

**Syntax:**

```vb 
Public Sub SetReportFooter(ByVal ParamArray str_Line() As String)
```

It takes a parameter array, so you can add as many footer lines as you want, delimited by comma ",".

**Example:** 

```vb
oRep.SetReportFooter("This is your report footer Section", "You can add here as many lines as you want") 
```

## PopulateReport Function

The PopulateReport function is responsible for viewing the report, so it must be your last assignment.

**Syntax:** 

```vb
Public Sub PopulateReport(ByRef ReportTable As ADODB.Recordset)
```

ReportTable parameter is a recordset used to populate the report.

**Example:**

```vb
Dim oMaster As New ADODB.Recordset()
Dim CN As New ADODB.Connection()

CN.Open("DCDR_NWind")
oMaster.Open("Select * from orders", CN, oMaster.CursorType.adOpenKeyset, oMaster.LockType.adLockOptimistic)

oRep.PopulateReport(oMaster) ' This must be your last assignment 
```
