﻿# **DynamicComponents - Dynamic Report-----**

Powered by ![](Aspose.Words.c0851dff-23e4-4178-a7c9-675532d3cb27.001.png)


# **System Requirements -----**
DC.DynamicReport runs as a COM class for included in any developing langauge support COM based application as  Visual Basic , Visual C++ , Borland C++ , Delphi  and others ..
# **Installing DC.DynamicReport-----**
The DC.DynamicReport setup program will automatically register the DC\_DynamicReport10.dll file on your system. 

There is no need to manually run RegSvr32.exe on your development system. 
# **Including DC.DynamicReport**
-----
To include DC.DynamicReport in your project  

1. From Project menu select add reference 
1. Push Browse button to locate your DC\_DynamicReport10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32)  , now the specific DLL included in your references
# **Deploying DC.DynamicReport-----**
There are two only files need to be distributed with DC.Num2Text COM based applications

- ` `DC\_Dynamic Report10 .dll
- DC\_DynamicReport\_Theme.dat

this files should be copied to the WinSystem directory which by default is C:\Windows\System32 
# **InitReport Function-----**
InitReport Function , must be your first assignment , an error may occur if you do not

We support eastern languages in all of our components , so Dynamic Report comes with support for right to left orientation

**Syntax:**
Public Sub InitReport(ByVal Right2Left As Boolean)
it takes 1 parameter
1-Right2Left define orientation , if true , this is usuful for eastern language use right orientation 


**Example:**
oRep.InitReport(False)







# **ReadTheme Function-----**
ReadTheme function enables you to select from 7 diffrent themes 
by chanhing theme you change whole appearance of report**


**Syntax:**

Public Sub ReadTheme(ByVal int\_ThemeID As Theme\_ID)
int\_ThemeID  may take any value from 1 to 6
Classic = 1
Blue = 2
Red = 3
Green = 4
Simple = 5
Transparent = 6

**Example:**

oRep.ReadTheme(DynamicComponents.DynamicReport.Theme\_ID.Classic) ' if ignored it is by default classic theme







# **LogoImage Function-----**
LogoImage enables you set your company logo

**Syntax:**
Public Sub LogoImage(ByVal str\_LogoFile As String, ByVal str\_LogoPath As String)
it takes 2 parameters
1-str\_LogoFile is logo file name
2- str\_LogoPath is logo file path

**Example:**
oRep.LogoImage("Logo.bmp",  "C:\Images\")







# **SetTitle Function-----**
SetTitle enables you set the title of the report

**Syntax:**
Public Sub SetTitle(ByVal str\_Title As String)


**Example:**
oRep.SetTitle("Customers List")







# **SetReportHeader Function-----**
SetReportHeader enables you set your report header lines , you can add as many lines as you want

**Syntax:**
Public Sub SetReportHeader(ByVal ParamArray str\_Line() As String)
it takes a  parameter array , so you can add as many header line as you want , delimetered by comma ","

**Example:**
oRep.SetReportHeader("This is Dynamic Report v1.0", "It is powered by EgyFirst inc.", "Dynamic Components is a trade mark since 2004")







# **GroupBy Function-----**
GroupBy function enables you set grouping data  , you can add as many lines as you want

**Syntax:**
Public Sub GroubBy(ByVal str\_GroupField As String, ByVal ShowGroupNavigator As Boolean, ByVal ForceNewPage As Boolean)

it takes 3 parameters
1-str\_GroupField parameter is the field used to grouping data
2- ShowGroupNavigator parameter determine if you want to show a group navigator or not 
group navigator enables you to go to directly to selected group
3- ForceNewPage  parameter , if true ,  every group will be viewing and printing in a new page


**Example:**
oRep.GroubBy("OrderID", True, True)







# **SumFields Function-----**
SumFields function enables you to sum defined fields** 

**Syntax:**

Public Sub SumFields(ByRef ReportTable As ADODB.Recordset, ByVal ParamArray str\_Line() As String)
it takes 2 parameters
1-ReportTable  parameter is a recordset used to populate report
2- str\_Line  is a  parameter array , so you can add as many summed fields  as you want , delimetered by comma ","

**Example:**

Dim oMaster As New ADODB.Recordset()
Dim CN As New ADODB.Connection()

CN.Open("DCDR\_NWind")
oMaster.Open("Selelct \* from orders", CN, oMaster.CursorType.adOpenKeyset, oMaster.LockType.adLockOptimistic)

oRep.SumFields(oMaster, "Quantity","Value")







# **SetCaption Function-----**
SetCaption  function enables you set caption for fields which may differ from its names
this mean a field named "ID" may get a new caption like "Customer ID"

**Syntax:**
Public Sub SetCaption(ByVal ParamArray str\_Line() As String)
it takes a  parameter array , so you can add as many caption as you want , delimetered by comma ","

**Example:**
oRep.SetCaption("Order ID", "Product ID", "Product Name", "Unit Price", "Quantity", "Discount")







# **SetReportFooter Function-----**
SetReportFooter enables you set your report footer lines , you can add as many lines as you want

**Syntax:**
Public Sub SetReportFooter(ByVal ParamArray str\_Line() As String)
it takes a  parameter array , so you can add as many header line as you want , delimetered by comma ","

**Example:**
oRep.SetReportFooter("This is your report footer Section", "you can add here as many lines as you want")







# **PopulateReport Function-----**
PopulateReport function is the function responsible for viewing report , so it must be your last assignment

**Syntax:**

Public Sub PopulateReport(ByRef ReportTable As ADODB.Recordset)
ReportTable  parameter is a recordset used to populate report

**Example:**

Dim oMaster As New ADODB.Recordset()
Dim CN As New ADODB.Connection()

CN.Open("DCDR\_NWind")
oMaster.Open("Selelct \* from orders", CN, oMaster.CursorType.adOpenKeyset, oMaster.LockType.adLockOptimistic)

oRep.PopulateReport(oMaster) '' this must be your last assignment









# **Contact us -----**
Home Page:      [ http://www.tools4vb.com](http://www.tools4vb.com)

Sales Email:     [sales@tools4vb.com](mailto: sales@tools4vb.com)

Support Email:  <support@tools4vb.com>
# **License -----**
Copyright ©2004 DynamicComponenets Software. All rights reserved

The software described in this document is furnished under a license agreement and may be used or copied only in accordance with the terms of the agreement. 

YOU MAY: 

\1. Install and use the unlimited number of copies of the TRIAL VERSION.

\2. Use one or more copies of the TRIAL VERSION for evaluation purposes only. 

\3. Copy and distribute freely the TRIAL VERSION 

YOU MAY NOT: 

\1. Sublicense, rent or lease the TRIAL VERSION or any portion of it. 

\2. Decompile, disassemble, reverse engineer or modify the TRIAL VERSION 


DISTRIBUTION: 

You are hereby licensed to make as many copies of the TRIAL VERSION as you wish and distribute them to anyone provided that all files are intact. You must distribute the install form of the TRIAL VERSION (not the files resulting of an installation). 

You are not allowed to sell the TRIAL VERSION 

Computer's Magazines are authorized to distribute it on any Cover Disk or CD-ROM without any permission. Please inform us by e-mail . 
# **How to order -----**
![](Aspose.Words.c0851dff-23e4-4178-a7c9-675532d3cb27.002.png)

Check the [http://www.tools4vb.com](http://www.tools4vb.com/Order%20Now.htm) for the latest pricing and product information. 

you can buy this product online easily and securely and you will get the registration key immediately.
# **How to Register your Copy**
-----
1. After your request  we will email you with registration key
1. Enter your  name and registration key , and enjoy programming with DC.DynamicReport


# **Author Informaion-----**
Company : **EgyFirst Software , inc**.

URL : <http://www.tools4vb.com>

Product : **DC DynamicReport**

Version: **1.0**
