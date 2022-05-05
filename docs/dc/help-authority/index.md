﻿# **DynamicComponents - Help Authority-----**

Powered by ![](Aspose.Words.ae3310bc-06aa-44b7-b32c-bb0578e2b47e.001.png)


# **Overview**
-----
DC.HelpAuthority is a COM based component that allows you to assign a sensitive help for every control in within your form or even every column in your grid  

DC.HelpAuthority may be used with any  developing language support COM based application like Visual Basic,Visual C++,Borland C++,Delphi and others ..

EgyFirst has done a lot of work for you. now you can develop your application and make it comprehensive by supporting it with your sensitive help
# **Features -----**
DC.HelpAuthority enables you to put the finish touch to your application by adding sensetive help to every control in your form , any column in your grid 
when you press F12 key this will trigger your sensitive help for focused control or column

**Example:**

Dim HA As New DynamicComponents.HelpAuthority()

HA.[PrepareHelp](#chmtopic8)(CN, Me, Me.AxDataGrid1)

![](Aspose.Words.ae3310bc-06aa-44b7-b32c-bb0578e2b47e.002.png)


# **System Requirements -----**
DC.HelpAuthority runs as a COM class for Developing with Visual Basic.Net under Microsoft Windows 98/NT/ 2000 or Windows XP. 


# **Installing DC.HelpAuthority-----**
The DC.HelpAuthority setup program will automatically register the DC\_HelpAuthority10.dll file on your system. 

There is no need to manually run RegSvr32.exe on your development system. 
# **Including DC.HelpAuthority**
-----
To include DC.HelpAuthorityin your project 

1. From Project menu select add reference 
1. Push Browse button to locate your DC\_HelpAuthority10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32)  , now the specific DLL included in your references


# **Deploying DC.HelpAuthority Applications** 
-----
There are two files need to be distributed with DC.HelpAuthority COM applications

- ` `DC\_HelpAuthority10.dll
- DCHA10\_Lang.dll

this files should be copied to the WinSystem directory which by default is C:\Windows\System32 
# **PrepareHelp**
# -----
Prepare form to know every thing about the form and its controls and all binding information 

**syntax:**

Function PrepareHelp(ByRef dm\_DSN As ADODB.Connection, ByRef dm\_Form As System.Windows.Forms.Form, Optional ByRef dm\_Grid As AxMSDataGridLib.AxDataGrid = Nothing)

dm\_DSN  is a reference to your DSN connection

dm\_Form is a reference to your form which passed as 'Me' keyword

Optional dm\_Grid (if your form has a grid) is a reference to your grid


**Example:**

Dim HA As New DynamicComponents.HelpAuthority()

HA.PrepareHelp(CN, Me, Me.AxDataGrid1)

where CN   is a reference to your DSN connection
and Me is a reference to your form which passed as 'Me' keyword
and AxDataGrid1 (if your form has a grid) is a reference to your grid



![](Aspose.Words.ae3310bc-06aa-44b7-b32c-bb0578e2b47e.002.png)
# **Sensitive F12 Help -----**
When you press F12 Key , this trigger a sensitive help ,this require

1. Create a new table , name it "Help" and put it in your database 
1. create 4 fields as specified

|Name|Type|Length|
| :- | :- | :- |
|Tag|Text|50|
|Id|Text|50|
|Description|Text|50|
|Contents|Memo||
`    `3. Fill Tag field with your [Form Tag](JavaScript:popup.TextPopup\(popuptxt1,popupfont1,9,9,-1,-1\))

`    `4. Fill Id Field with your control name 

`   `5. Fill Id Field with DataGrid name followed with underscore character "\_" , which will be something like this  

`       `"axDatagrid\_ProductId"

`    `6. Fill Description field with your control Description

`    `7. Fill Contents field with your supported help for this control

**Note:**

`       `To change your form text put form name in both field tag and id

![](Aspose.Words.ae3310bc-06aa-44b7-b32c-bb0578e2b47e.002.png)


# **Configuration Utility**
-----
We supply you with Configuration Utility which enable you to assign your own language used with DC.HelpAuthority

![](Aspose.Words.ae3310bc-06aa-44b7-b32c-bb0578e2b47e.003.png)




# Tutorial
-----
This tutorial describe most of features supported by DC.HelpAuthority

also you can refer to the project  example which installed by default into C:\Program Files\Dynamic Components\Help Authority\Tutorial\



Dim HA As New DynamicComponents.HelpAuthority()

Dim CN As New ADODB.Connection()

Dim oOrders As New ADODB.Recordset()

Dim oOrderDetails As New ADODB.Recordset()

Dim oAccess As New Access.Application()

Dim DAO\_DBEngine As New DAO.DBEngine()

'Press F12 to get help to any control on your form



Private Sub TestForm\_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

'establish DSN

oAccess.DBEngine.RegisterDatabase("DCDM\_Nwind", "Microsoft Access Driver (\*.mdb)", True, "DBQ=" & VB6.GetPath & "\Nwind.mdb")

CN.Open("DSN=DCDM\_NWind")

oOrders.Open("Orders", CN, oOrders.CursorType.adOpenKeyset, oOrders.LockType.adLockOptimistic)

oOrderDetails.Open("OrderDetails", CN, oOrderDetails.CursorType.adOpenKeyset, oOrderDetails.LockType.adLockOptimistic)

PopulateDate()

Me.AxDataGrid1.DataSource = oOrderDetails

HA.PrepareHelp(CN, Me, Me.AxDataGrid1)

End Sub
# **Contact us -----**
Home Page:      <http://www.dynamic-components.com>

Sales Email:     <sales@dynamic-components.com>

Support Email:  <support@dynamic-components.com>
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
![](Aspose.Words.ae3310bc-06aa-44b7-b32c-bb0578e2b47e.004.png)

Check the [http://www.tools4vb.com](http://www.tools4vb.com/Order%20Now.htm) for the latest pricing and product information. 

you can buy this product online easily and securely and you will get the registration key immediately.
# **How to Register your Copy**
-----
1. After your request  we will email you with registration key
1. Enter your  name and registration key , and enjoy programming with DC.HelpAuthority


# **Author Informaion-----**
Company : **EgyFirst Software , inc**.

URL : <http://www.dynamic-components.com>

Product : **DC Help Authority**

Version: **1.0**
