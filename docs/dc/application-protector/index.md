DC-Application Protector
===========


Overview
---------

- DC.AppProtecor is a library that allows you to protect Windows executable files against piracy. Using multi level encryption algorithms .  Thanks to Nested Layers Protection (NLP), new protection technology we adapt in our protection system.

- DC.AppProtecor Dialog box is generated on the fly so any hackers attempt to remove its resource  will fail.  It can be used with any  developing language support COM based application like Visual Basic,Visual C++,Borland C++,Delphi and others.

- DC.AppProtecor allows you to release your trail version with its restriction of days limit. It has 3 levels of encryption algorithms , with about 50 million collection ,each encryption algorithms of this 50 million collection has huge variety of activation key to generate.

- If you are  losing sales to software , stop it now by our advanced, secure software protection system. It is very easy to include in your developing project  with only 3 lines of code .  EGY1ST has done a lot of work for you. You define few lines of code and we keep you safe away from hackers attempt. 

Features 
----------

Do you know that DC.AppProtector itself is protected by itself !?. Few  Lines to add in your Form\_Load event  and you will get full secure software protection system.

**You can:**

- Define your multi level encryption algorithms.
- Define your Free Trail days limit
- Define your customized message appears on protection dialog box 
- Define your URL where customers can purchase your product

**Example:**

Dim MyProtection As New DynamicComponents.AppProtector()

Dim ProductName As String

Dim CompanyInfo As String

// Customized author message

CompanyInfo = "Company Name: EgyFist Software , inc." + vbCrLf    // vbCrLf  force new line

CompanyInfo += "Home Page: htpp://www.egyfirst.com" + vbCrLf

CompanyInfo += "License: Free 30 Days Trail Version"

ProductName = "DC AppProtector v1.0"

// Code of Protection

MyProtection.[SetInformation](#chmtopic8)(ProductName, CompanyInfo, "https://example.com/buynow/")

MyProtection.[SetAlgorithms](#chmtopic9)(1234, 56, 78)

MyProtection.[SetLicense](#chmtopic10)( 30)   // may be  ignored , since it is by default 30 days

MyProtection.[ShowAuthor](#chmtopic11)()

Now you can generate huge numbers of  activation key using [Activation Key Utility](#chmtopic13)
## System Requirements
DC.AppProtector runs as a COM class for included in any developing langauge support COM based application as  Visual Basic , Visual C++ , Borland C++ , Delphi  and others.
## Installation

The DC.AppProtector setup program will automatically register the DC\_AppProtector10.dll file on your system.  There is no need to manually run RegSvr32.exe on your development system. 

## Including DC.AppProtector

To include DC.AppProtector in your project  

1. From Project menu select add reference 
1. Push Browse button to locate your AppProtector10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32)  , now the specific DLL included in your references

## Deploying DC.AppProtector

The only file needs to be distributed with DC.AppProtector COM applications is DC\_AppProtector10 .dll

this file should be copied to the WinSystem directory which by default is C:\Windows\System32 

## How to Use

**SetInformation Function**

SetInformation function enables you to  Define your customized message appears on protection dialog box.
it include s3 parameters

1. Product info
1. Company info
1. URL where customers can purchase your product by clicking Buy Now Button on Protection dialog box

**Syntax:**

> SetInformation(ByVal str\_ProductName As String, ByVal str\_CompanyInfo As String, ByVal str\_BuyNow\_URL As String)

**Example:**

Dim CompanyInfo As String

CompanyInfo = "Company Name: EgyFirst Software , inc." + vbCrLf  //'vbcrlf force new line

CompanyInfo += "Home Page: htpp://www.egyfirst.com" + vbCrLf

CompanyInfo += "License: Free 30 Days Trail Version"

MyProtection.SetInformation("DC AppProtector v1.0", CompanyInfo, "http://www.egyfirst.com/buynow/")

**SetAlgorithms Function**

Encryption Algorithms define the method DC.AppProtecor adapt to generate its activation keys related to it.

DC.AppProtecor has 4 levels of encryption algorithms 

1. ` `first level has 6000 choices           (must be between 1000 and 7000)
2. ` `second  level has 90 choices         (must be between 10 and 99)
3. Third  level has 90 choices             (must be between 10 and 99)
4. Fourth level is a string                     (must be 7 characters length)

if you develop more than one product and protect them all with the same DC.AppProtector , then  every product  must  dedicated with a different id, so first product may have algorithms like (1234, 56, 78,"abcdefg")  and second product may have algorithms like (1234, 56, 78,"aaabccc") and third product may have algorithms like (5555, 66, 77,"egyfirst"). This means you can define similar or different algorithms to multi protected product  but every product must have unique ID which defined by int\_Algorithms4 parameter

**Caution:**

> if you develop more than one product and protect them all with the same product id , then any registration to one of them will register the rest

**Syntax:**

> SetAlgorithms(ByVal int\_Algorithms1 As Integer, ByVal int\_Algorithms2 As Integer, ByVal int\_Algorithms3 As Integer, ByVal str\_Algorithms4 As string)

**Example:**

SetAlgorithms(1234, 56, 78,"abcdefg")

**SetLicense Function**

SetLicense Function enables you to define trail version days limit if this assignment ignored , it will be by default 30 days.

**Syntax:**

Public Sub SetLicense(ByVal int\_DaysLimit As Integer )

**Example:**

SetLicense(15)

 **ShowAuthor Function**

This function is the heart of  your protection and it is responsible to popup the protection dialog box this function must be called at the end end of your protection code block

**Syntax:**

Function ShowAuthor() 
No Parameter required with his function

**Example**:

ShowAuthor() 

**NotLicensed-----**
NotLicensed is public variable addicte to state of your product license , so you can do the proper action 
it will be True if  protected product is registered  or within trial period .

**Syntax**:

Public NotLicensed As Boolean = False

**Example**:

Dim MyProtection As New DynamicComponents.AppProtector()

If  MyProtection.NotLicensed Then Exit Sub

**Activation Key Utility**
Using Activation Key utility you can generate huge numbers of randomize activation key depends on algorithms you use , so activation keys collection generated (for example) by SetAlgorithms(1234,56,78) will differ completely from one generated using SetAlgorithms(1111,11,11) and differ from any other algorithms  .

**Example:**

Here some activation keys generated using algorithms

SetAlgorithms(1234,56,78)                SetAlgorithms(1111,11,11)

2533-177-552-708-7856                    2167-115-069-275-1206
2670-209-627-395-7963                    2933-292-542-319-1226
2858-259-683-679-4606                    3781-640-481-975-8749
3210-373-873-517-1567                    3784-642-049-096-4889    
3331-419-780-812-0071                    3797-648-869-680-0506
2412-152-129-710-8440                    3767-633-202-668-7204
3451-468-894-209-3279                    3607-553-914-590-1600
2222-117-365-198-8042                    2381-153-727-457-2744
3193-367-706-720-5254                    3923-717-512-323-8126
2616-196-555-752-0925                    3805-653-091-025-3862

just remember that there are 50 millions Encrypted algorithms available for you to use, generated from any combination of (****,**,**)
where first algorithms must be between 1000 and 7000     ===>(7000 - 1000) ===> 6000 
and second algorithms must be between 10 and 90            ===>(90 - 10) ===> 80 
and third algorithms must be between 10 and 90               ===>(90 - 10) ===> 80 
This is (6000 * 80 * 80) ===> 4,800,000 different combination


Tutorial
---------

This tutorial describe all  features supported by DC.AppProtector

also you can refer to the project example which installed by default into C:\Program Files\Dynamic Components\Application Protector\Tutorial\

This code must be in first form loaded in your project 

``` vb
Private Sub TestForm\_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load

Dim MyProtection As New DynamicComponents.AppProtector()

Dim ProductName As String

Dim CompanyInfo As String

// Customized author message

CompanyInfo = "Company Name: EgyFist Software , inc." + vbCrLf    // vbCrLf  force new line

CompanyInfo += "Home Page: htpp://www.egyfirst.com" + vbCrLf

CompanyInfo += "License: Free 30 Days Trail Version"

ProductName = "DC AppProtector v1.0"

// Code of Protection

MyProtection.[SetInformation](#chmtopic8)(ProductName, CompanyInfo, "http://www.egyfirst.com/buynow/")

MyProtection.[SetAlgorithms](#chmtopic9)(1234, 56, 78)

MyProtection.[SetLicense](#chmtopic10)( 30)   // may be  ignored , since it is by default 30 days

MyProtection.[ShowAuthor](#chmtopic11)()

End Sub
```