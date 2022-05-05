# **DynamicComponents - ReturnKeyEnable-----**

Powered by ![](Aspose.Words.73bbce01-875a-4fb9-be3b-af906f986d16.001.png)


# **Overview**
-----
DC.ReturnKeyEnable is a COM based component that enables you navigate thriugh form controls using Retun key as with Tab Key  

DC.ReturnKeyEnable may be used with any  developing language support COM based application like Visual Basic,Visual C++,Borland C++,Delphi and others ..

EgyFirst has done a lot of work for you. no need to waste time , defining events to every control within your form to handle Return key press  
you design your form as usual and we allow you move through its controls as wanted
# **Features -----**
Only one line of code and you can move easily through your form controls without any additional programming  
**that is all !!**


**Example:**

RKE.[EnableReturnKey](#chmtopic8)(Me, True)  //' Now you can use Return Key to move through contols insted of  Tab Key
# **System Requirements -----**
DC.ReturnKeyEnable runs as a COM class for Developing with Visual Basic.Net under Microsoft Windows 98/NT/ 2000 or Windows XP. 


# **Installing DC.ReturnKeyEnable-----**
The DC.ReturnKeyEnable setup program will automatically register the DC\_ReturnKeyEnable10.dll file on your system. 

There is no need to manually run RegSvr32.exe on your development system. 
# **Including DC.ReturnKeyEnable** 
-----
To include DC.ReturnKeyEnable in your project 

1. From Project menu select add reference 
1. Push Browse button to locate your DC\_ReturnKeyEnable10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32)  , now the specific DLL included in your references


# **Deploying DC.ReturnKey Enable Applications -----**
The only file needs to be distributed with DC.ReturnKeyEnable COM applications is DC\_ReturnKeyEnable 10.dll

this file should be copied to the WinSystem directory which by default is C:\Windows\System32 
# **EnableReturnKey -----**
Enable you navigate through controls with Return key as with tab key

**Syntax:**

Function EnableReturnKey(ByVal Mode As Boolean)

**Example:**

RKE.EnableReturnKey(True)
# Tutorial
-----
This tutorial describe most of features supported by DC.ReturnKeyEnable 

also you can refer to the project  example which installed by default into C:\Program Files\Dynamic Components\ReturnKeyEnable\Tutorial\



Dim RKE As New DynamicComponents.ReturnKeyEnable()

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

RKE.EnableReturnKey(Me, True)  //' Now you can use Return Key to move through contols insted of  Tab Key

End Sub


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
![](Aspose.Words.73bbce01-875a-4fb9-be3b-af906f986d16.002.png)

Check the [http://www.tools4vb.com](http://www.tools4vb.com/Order%20Now.htm) for the latest pricing and product information. 

you can buy this product online easily and securely and you will get the registration key immediately.
# **How to Register your Copy**
-----
1. After your request  we will email you with registration key
1. Enter your  name and registration key , and enjoy programming with DC.DataManger


# **Author Informaion-----**
Company : **EgyFirst Software , inc**.

URL : <http://www.tools4vb.com>

Product : **DC ReturnKeyEnable**

Version: **1.0**
