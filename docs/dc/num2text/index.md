DC Num2Text
=============

Overview
---------

DC.Num2Text is a COM-based component that converts numerical values into words in 4 languages.
For example, the numerical value **7431285.46** would be translated into the text:


In English it will be:
Seven millions, four hundred and thirty one thousand, two hundred and eighty five dollars and forty six cents.

In French it will be:  
Sept millions, quatre cents et trente un milliers, deux cents et quatre-vingt cinq euro et quarante six cents.

In German it will be:
Sieben Millionen, vier Hunderte eins und dreiβig Tausenden, zwei Hunderte fünf und achtzig euro sechs und vierzig cents.  

In Arabic it will be:
![](images/Aspose.Words.b3394690-9aa4-4836-a76e-f075b60016c5.002.png)

**The most useful use of** DC.Num2Text **is with Cheque Production Systems and financial reports in business applications.**

EgyFirst has done a lot of work for you. You define your number and we translate it to your preferred language.

## **Features**

For now DC.Num2Text can convert your number into 4 languages (Arabic-English-French-German) 

**But we** are looking to get feedback from our customers and we will prioritize our development efforts based on customer requirements. 

Just [email us](mailto:support@egyfirst.com) with your language & concept used in counting with several examples.

**Example:**

```
Dim oTextNum As New DynamicComponents.Num2Text()

Dim strNum As String

strNum = oTextNum.[TranslateNumber](#chmtopic8)("159584.58", Num2Text.Language_ID.English) // Translate into English
```

## **System Requirements**

DC.Num2Text runs as a COM class for inclusion in any COM based developing languages like Visual Basic, Visual C++, Borland C++, Delphi and others.

## **Installing DC.Num2Text**

The DC.Num2Text setup program will automatically register the DC_Num2Text10.dll file on your system.  

There is no need to manually run RegSvr32.exe on your development system.

## **Including DC.Num2Text**

To include DC.Num2Text in your project:

1. From Project menu select Add Reference.
2. Click Browse button to locate your AppProtector10.DLL file which by default is located in [c:\windows\system32](file:///c:/windows/system32). Now the specific DLL is included in your references.

## **Deploying DC.Num2Text**

The only file that needs to be distributed with DC.Num2Text COM based applications is DC_Num2Text10.dll. 

This file should be copied to the WinSystem directory which by default is C:\Windows\System32.

## **TranslateNumber Function**

TranslateNumber is the function responsible for translating numbers into the proper language.

**Syntax:**

```
Public Function TranslateNumber(ByVal str_Number As String, ByVal Lang As Language_ID) As String
```

It takes 2 parameters:
- The first parameter is the number wanted to translate.
The second parameter is language ID where:
  - 1 means translating into Arabic Language.
  - 2 means translating into English Language.
  - 3 means translating into the French Language.
  - 4 means translating into the German Language. 

**Example:**

```
Dim strNum = TranslateNumber("49562854", 3) // Translate into French language
```

## **SetCurrency Function**

The SetCurrency function enables you to customize your currency. 

The default currency used by the English language is the Dollar, while the Euro is the default currency for French and German Languages, and![](images/Aspose.Words.b3394690-9aa4-4836-a76e-f075b60016c5.003.png) is the default currency for the Arabic Language.

**Syntax:**

```
Public Sub SetCurrency(ByVal str_Currency As String, ByVal str_CurrencyUnit As String, ByVal str_CurrencyPlural As String, ByVal str_CurrencyUnitPlural As String)
```

This function takes 4 parameters:
- The first parameter str_Currency is your customized currency in singular form.  
- The second parameter str_CurrencyUnit is your customized currency unit in singular form.
- The third parameter str_CurrencyPlural is your customized currency in plural form.
- The fourth parameter str_CurrencyUnitPlural is your customized currency unit in plural form.

**Example:** 

```
SetCurrency("pound", "piaster", "pounds", "piasters")
```

When you use [TranslateNumber](#chmtopic8) function, the result may be something like:

Four hundred and twenty one pounds and twenty three piasters

## Tutorial

This tutorial describes all the features supported by DC.Num2Text. 

You can also refer to the project example which is installed by default into C:\Program Files\Dynamic Components\Num2Text\Tutorial\

```
Dim oTextNum As New DynamicComponents.Num2Text()

Dim strNum As String 

oTextNum.SetCurrency("Dollar", "Cent", "Dollars", "Cents")

strNum = oTextNum.[TranslateNumber](#chmtopic8)("159584.58", DynamicComponents.Num2Text.Language_ID.English) // Translate into English
```
