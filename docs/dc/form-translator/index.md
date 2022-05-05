# **DynamicComponents - Form Translator-----**

Powered by ![](Aspose.Words.d68589ff-bca5-455c-9b10-b6946f286dbf.001.png)


# **Overview**
-----
DC.FormTranslator is a COM based component that allows you Support MultiLanguage Application , by populate form labels with predefined translation automatically  

DC.FormTranslator may be used with any  developing language support COM based application like Visual Basic,Visual C++,Borland C++,Delphi and others ..

EgyFirst has done a lot of work for you. no need to waste time , designing your form again to support multi languages and eastern languages application 
you design one form and we design the other by translating it for you
# **Features -----**
If you develop multi language application or eastern language application , you must get DC.FormTranslator
Only one  Line to add in your Form\_Load event  and we will translate  the form with all its labels for you  

**Note:**
It is recommended to use DC.FormFlipper with DC.FormTranslator

**Example:**

Dim FT as DynamicComponents.FormTranslator()

FT.[TranslateForm](#chmtopic8)(Me, CN, 2) 'Trnslate form into French 

where CN is your DSN , and parameter 2 is language id , here it refer to French language



\1) First image show orginal form in English

![](Aspose.Words.d68589ff-bca5-455c-9b10-b6946f286dbf.002.png)



\2) Second image show form after translating  it into french

![](Aspose.Words.d68589ff-bca5-455c-9b10-b6946f286dbf.003.png)
# **System Requirements -----**
DC.FormTranslator runs as a COM class for Developing with Visual Basic.Net under Microsoft Windows 98/NT/ 2000 or Windows XP. 


# **Installing DC.FormTranslator-----**
The DC.FormTranslator setup program will automatically register the DC\_FormTranslator10.dll file on your system. 

There is no need to manually run RegSvr32.exe on your development system. 
# **Including DC.FormTranslator**
-----
To include DC.FormTranslator in your project 

1. From Project menu select add reference 
1. Push Browse button to locate your DC\_FormTranslator10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32)  , now the specific DLL included in your references


# **Deploying DC.FormTranslator Applications -----**
The only file needs to be distributed with DC.FormTranslator COM applications is DC\_FormTranslator10.dll

this file should be copied to the WinSystem directory which by default is C:\Windows\System32 
# **TranslateForm**
-----
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
`    `3. Fill Tag field with your Form Name

`    `4. Fill Id Field with your Label  name

`    `5. Fill Language1 field with your first language translation

`    `6.  Fill Language2  field with your second  language translation and so on , you can add many    

`         `languages as you like , no limitation !

**Note:**

to change form text put form name in both field tag and id

**Syntax:**

Function  TranslateForm(ByRef dm\_Form As System.Windows.Forms.Form, ByRef dm\_DSN As ADODB.Connection, ByVal dm\_Language As Byte)

**Example:**

FT.TranslateForm(Me, CN, 2) 'Trnslate form into French 

This will populate your form text and all its labels with your translation in field "Languge2" in table "Multilanguage" in database refered to it by DSN named CN in this example

Example of French Translation

![](TranslateForm.gif)




# Tutorial
-----
This tutorial describe most of features supported by DC.FormTranslator

also you can refer to the project  example which installed by default into C:\Program Files\Dynamic Components\Form Translator\Tutorial\





Dim FT As New DynamicComponents.FormTranslator()

Dim CN As New ADODB.Connection()

Dim oOrders As New ADODB.Recordset()

Dim oAccess As New Access.Application()

Dim DAO\_DBEngine As New DAO.DBEngine()



Private Sub TestForm\_Load(ByVal eventSender As System.Object, ByVal eventArgs As System.EventArgs) Handles MyBase.Load

'establish DSN

oAccess.DBEngine.RegisterDatabase("DCDM\_Nwind", "Microsoft Access Driver (\*.mdb)", True, "DBQ=" & VB6.GetPath & "\Nwind.mdb")

CN.Open("DSN=DCDM\_NWind")

oOrders.Open("Orders", CN, oOrders.CursorType.adOpenKeyset, oOrders.LockType.adLockOptimistic)

PopulateDate()

FT.TranslateForm(Me, CN, 2) 'Trnslate form into French 

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
![](Aspose.Words.d68589ff-bca5-455c-9b10-b6946f286dbf.004.png)

Check the [http://www.tools4vb.com](http://www.tools4vb.com/Order%20Now.htm) for the latest pricing and product information. 

you can buy this product online easily and securely and you will get the registration key immediately.
# **How to Register your Copy**
-----
1. After your request  we will email you with registration key
1. Enter your  name and registration key , and enjoy programming with DC.DataManger


# **Author Informaion-----**
Company : **EgyFirst Software , inc**.

URL : <http://www.tools4vb.com>

Product : **DC FormTranslator**

Version: **1.0**
