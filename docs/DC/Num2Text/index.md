# **DynamicComponents - Num2Text-----**

Powered by ![](Aspose.Words.b3394690-9aa4-4836-a76e-f075b60016c5.001.png)


# **Overview**
-----
DC.Num2Text  is a COM based component that convert numerical values into words in 4 languages
For example, the numerical value **7431285.46**  would be translated into the text 


in English will be:
Seven millions , four hundreds and thirty one thousands , two hundreds and eighty five dollars and forty six cents 

in French will be:
Sept millions , quatre cents et trente un milliers , deux cents et quatre-vingt cinq euro et quarante six cents 

in German will be:
Sieben Millionen , vier Hunderte eins und dreiكig Tausenden , zwei Hunderte fünf und achtzig euro sechs und vierzig cents 

in Arabic will be:
![](Aspose.Words.b3394690-9aa4-4836-a76e-f075b60016c5.002.png)

**the most useful use** DC.Num2Text  **is with  Cheque Production Systems and finical reports in business application .**

EgyFirst has done a lot of work for you. You define your number and we translate it to your preferred language. 
# **Features -----**
for Now DC.Num2Text can convert your number into 4 languages (Arabic-English-French-German)

**but we**  are looking to get feedback from our customers and we will prioritise the our development efforts based on customer requirements.

Just :[email us](mailto:support@egyfirst.com) with your language & concept used  in counting with several examples.

**Example:**

Dim oTextNum As New DynamicComponents.Num2Text()

dim strNum as string

strNum  = oTextNum.[TranslateNumber](#chmtopic8)("159584.58", Num2Text.Language\_ID.English) // translate into English


# **System Requirements -----**
DC.Num2Text runs as a COM class for included in any developing langauge support COM based application as  Visual Basic , Visual C++ , Borland C++ , Delphi  and others ..
# **Installing DC.Num2Text-----**
The DC.Num2Text setup program will automatically register the DC\_Num2Text10.dll file on your system. 

There is no need to manually run RegSvr32.exe on your development system. 
# **Including DC.Num2Text**
-----
To include DC.Num2Text in your project  

1. From Project menu select add reference 
1. Push Browse button to locate your AppProtector10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32)  , now the specific DLL included in your references
# **Deploying DC.Num2Text-----**
The only file needs to be distributed with DC.Num2Text COM based applications is DC\_Num2Text10 .dll

this file should be copied to the WinSystem directory which by default is C:\Windows\System32 
# **TranslateNumber Function-----**
TranslateNumber  is the function responsible for translating numbers into proper language

**Syntax:**

Public Function TranslateNumber(ByVal str\_Number As String, ByVal Lang As Language\_ID) As String

it takes 2 parameters
first parameter is number wanted to translate
second parameter is language ID
where 1 mean translating into  Arabic Language
`          `2 mean translating into  English Language
`          `3 mean translating into  French Language
`          `4 mean translating into  German Language

**Example:**

dim strNum  = TranslateNumber ("49562854",3)  // translate into French language




# **SetCurrency Function**
-----
SetCurrency function enables you customize your currency 

default currency used by English language is Dollar , while Euro is default currency for French and German Languages , and ![](Aspose.Words.b3394690-9aa4-4836-a76e-f075b60016c5.003.png) is default currency for Arabic Language

**Syntax:**

Public Sub SetCurrency(ByVal str\_Currency As String, ByVal str\_CurrencyUnit As String, ByVal str\_CurrencyPlural As String, ByVal str\_CurrencyUnitPlural As String)

this function takes 4 Parameters
first parameter str\_Currency  is your customized currency in single 
first parameter str\_CurrencyUnit is your customized currency unit in single 
first parameter str\_CurrencyPlural is your customized currency in plural
first parameter str\_CurrencyUnitPlural is your customized currency in plural

**Example:**

SetCurrency("pound","piaster","pounds","piasters") 

when you use [TtranslateNumber](#chmtopic8) function , result may be something like that
four hundreds and twenty one pounds and twenty three piasters




# Tutorial
-----
This tutorial describe all  features supported by DC.Num2Text

also you can refer to the project example which installed by default into C:\Program Files\Dynamic Components\Num2Text\Tutorial\



dim oTextNum As New DynamicComponents.Num2Text()

dim strNum as string

oTextNum.SetCurrency("Dollar", "Cent", "Dollars", "Cents")

strNum  = oTextNum.[TranslateNumber](#chmtopic8)("159584.58", DynamicComponents.Num2Text.Language\_ID.English) // translate into English


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
![](Aspose.Words.b3394690-9aa4-4836-a76e-f075b60016c5.004.png)

Check the [http://www.tools4vb.com](http://www.tools4vb.com/Order%20Now.htm) for the latest pricing and product information. 

you can buy this product online easily and securely and you will get the registration key immediately.
# **How to Register your Copy**
-----
1. After your request  we will email you with registration key
1. Enter your  name and registration key , and enjoy programming with DC.Num2Text


# **Author Informaion-----**
Company : **EgyFirst Software , inc**.

URL : <http://www.tools4vb.com>

Product : **DC Num2Text**

Version: **1.0**
