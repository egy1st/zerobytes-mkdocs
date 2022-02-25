﻿# **DynamicComponents - Image Button-----**

Powered by ![](Aspose.Words.0607795d-0f5c-44d4-95ed-bee8978b477f.001.png)


# **System Requirements -----**
DC.ImageButton runs as a COM class for Developing with Visual Basic.Net under Microsoft Windows 98/NT/ 2000 or Windows XP. 


# **Installing DC.ImageButton-----**
The DC.ImageButton setup program will automatically register the DC\_Image Button10.dll file on your system. 

There is no need to manually run RegSvr32.exe on your development system. 
# **Including DC.ImageButton**
-----
To include DC.ImageButton in your project 

1. From Project menu select add reference 
1. Push Browse button to locate your DC\_ImageButton10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32)  , now the specific DLL included in your references


# **Deploying DC.ImageButton Applications** 
-----
The only file needs to be distributed with DC.FormFlipper COM applications is DC\_FormFlipper10.dll

this file should be copied to the WinSystem directory which by default is C:\Windows\System32 
# **PrepareImageButtons -----**
This function enables you to  assign icons path for  button image , additionally ,you can assign a motion for each button if you put second parameter to true 

**Syntax:**

Function PrepareImageButtons(ByVal ImageFullPath As String, ByVal Motion As Boolean)

where ImageFullPath parameter is the path to your button icons
and Motion  parameter determine if you want assign a motion to your button icons or not



**Example:**

IB.PrepareImageButtons("C:\MyApp\Icons\", True)

where "[C:\MyApp\Icons\](file:///C:/MyApp/Icons/)" is the path to your button icons
and you detrmine your buttons to has a motion action 



- Buttons without Motion

![](Aspose.Words.0607795d-0f5c-44d4-95ed-bee8978b477f.002.png)    

- Buttons with Motion

![](Aspose.Words.0607795d-0f5c-44d4-95ed-bee8978b477f.003.png)


# **AddImageButton**
-----
Assign icons for every button state , when mouse over , mouse down , mouse up 

**Syntax:**

Public AddImageButton(ByRef ButtonName As Windows.Forms.Button, ByVal img\_MouseLeave As String, ByVal img\_MouseEnter As String, ByVal img\_MouseDown As String)

where img\_MouseLeave parameter is the icon appear where mouse leave button
and    img\_MouseEnter  parameter  is the icon appear where mouse over the button
and    img\_MouseDown parameter  is the icon appear where mouse pressed


**Example:**

Dim IB As New DynamicComponents.ImageButton()
IB.AddImageButton(Me.FirstButton, "first.ico", "firstover.ico", "firstdown.ico")
IB.AddImageButton(Me.PreviousButton, "previous.ico", "previousover.ico", "previousdown.ico")
IB.AddImageButton(Me.NextButton, "next.ico", "nextover.ico", "nextdown.ico")
IB.AddImageButton(Me.LastButton, "last.ico", "lastover.ico", "lastdown.ico")



- Buttons without Motion

![](file:///G:/Programms%20on%20D/Image%20Button/Help/ImageButtons.gif)    

- Buttons with Motion

![](file:///G:/Programms%20on%20D/Image%20Button/Help/ImageButtons2.gif)


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
![](Aspose.Words.0607795d-0f5c-44d4-95ed-bee8978b477f.004.png)

Check the [http://www.tools4vb.com](http://www.tools4vb.com/Order%20Now.htm) for the latest pricing and product information. 

you can buy this product online easily and securely and you will get the registration key immediately.
# **How to Register your Copy**
-----
1. After your request  we will email you with registration key
1. Enter your  name and registration key , and enjoy programming with DC.ImageButton


# **Author Informaion-----**
Company : **EgyFirst Software , inc**.

URL : <http://www.tools4vb.com>

Product : **DC Image Button**

Version: **1.0**
