# DC Application Protector

## Overview

- DC.AppProtector is a library that allows you to protect Windows executable files against piracy using multi-level encryption algorithms. Thanks to Nested Layers Protection (NLP), the new protection technology we adapted in our protection system.

- DC.AppProtector's dialog box is generated on the fly so any hacker's attempt to remove its resource will fail. It can be used with any developing language that supports COM based applications like Visual Basic, Visual C++, Borland C++, Delphi, and others.

- DC.AppProtector allows you to release your trial version with restrictions like a day limit. It has 3 levels of encryption algorithms, with about 50 million collections. Each encryption algorithm in this 50 million collection has a huge variety of activation keys that can be generated.

- If you are losing sales to software piracy, stop it now with our advanced, secure software protection system. It is very easy to include in your developing project with only 3 lines of code. EGY1ST has done a lot of work for you. You define a few lines of code and we keep you safe from hackers' attempts.

## Features

Do you know that DC.AppProtector itself is protected by itself!? Just a few lines need to be added in your Form_Load event and you will get a full, secure software protection system. 

**You can:**

- Define your multi-level encryption algorithms.
- Define your free trial days limit.
- Define your customized message that appears on the protection dialog box.
- Define your URL where customers can purchase your product. 

**Example:**

```vb
Dim MyProtection As New DynamicComponents.AppProtector()

Dim ProductName As String 

Dim CompanyInfo As String

' Customized author message

CompanyInfo = "Company Name: EgyFirst Software, inc." + vbCrLf    ' vbCrLf forces a new line  

CompanyInfo += "Home Page: http://www.egyfirst.com" + vbCrLf   

CompanyInfo += "License: Free 30 Day Trial Version"  

ProductName = "DC AppProtector v1.0"

' Code of Protection

MyProtection.SetInformation(ProductName, CompanyInfo, "https://example.com/buy") 

MyProtection.SetAlgorithms(1234, 56, 78)

MyProtection.SetLicense(30)   ' May be ignored, the default is 30 days   

MyProtection.ShowAuthor()
```

## System Requirements

DC.AppProtector runs as a COM class that can be included in any developing language that supports COM based applications like Visual Basic, Visual C++, Borland C++, Delphi, and others.

## Installation

The DC.AppProtector setup program will automatically register the DC_AppProtector10.dll file on your system. There is no need to manually run RegSvr32.exe on your development system.

## Including DC.AppProtector

To include DC.AppProtector in your project:

1. From the Project menu select Add Reference.
2. Click the Browse button to locate your AppProtector10.DLL file which by default is located in [c:\windows\system32](file:///c:/windows/system32). Now the specific DLL is included in your references.

## Deploying DC.AppProtector 

The only file that needs to be distributed with DC.AppProtector COM applications is DC_AppProtector10.dll.

This file should be copied to the WinSystem directory which by default is C:\Windows\System32.

## How to Use

### SetInformation Function

The SetInformation function enables you to define your customized message that appears on the protection dialog box. It includes 3 parameters:

1. Product info
2. Company info 
3. URL where customers can purchase your product by clicking the Buy Now button on the Protection dialog box

**Syntax:** 

```vb
SetInformation(ByVal str_ProductName As String, ByVal str_CompanyInfo As String, ByVal str_BuyNow_URL As String)
```

**Example:**

```vb
Dim CompanyInfo As String

CompanyInfo = "Company Name: EgyFirst Software, inc." + vbCrLf ' vbCrLf forces a new line

CompanyInfo += "Home Page: http://www.egyfirst.com" + vbCrLf  

CompanyInfo += "License: Free 30 Days Trial Version"

MyProtection.SetInformation("DC AppProtector v1.0", CompanyInfo, "https://www.egyfirst.com/buy")
```

### SetAlgorithms Function

Encryption algorithms define the method DC.AppProtector is used to generate its activation keys. 

DC.AppProtector has 4 levels of encryption algorithms:

1. First level has 6000 choices (must be between 1000 and 7000)
2. The second level has 90 choices (must be between 10 and 99) 
3. The third level has 90 choices (must be between 10 and 99)
4. Fourth level is a 7-character string 

If you develop more than one product and protect them all with the same DC.AppProtector, then every product must have a different ID. So the first product may have algorithms like (1234, 56, 78, "abcdefg") and the second product may have (1234, 56, 78, "aaabccc"). This means you can define similar or different algorithms for multiple protected products, but every product must have a unique ID defined by the int_Algorithms4 parameter.

**Caution:** If you develop more than one product and protect them all with the same product ID, then any registration to one will register the rest.

**Syntax:**

```vb 
SetAlgorithms(ByVal int_Algorithms1 As Integer, ByVal int_Algorithms2 As Integer, ByVal int_Algorithms3 As Integer, ByVal str_Algorithms4 As String)
```

**Example:** 

```vb
SetAlgorithms(1234, 56, 78, "abcdefg")
```

### SetLicense Function

The SetLicense function enables you to define the trial version days limit. If this assignment is ignored, it will default to 30 days. 

**Syntax:** 

```vb
Public Sub SetLicense(ByVal int_DaysLimit As Integer) 
```

**Example:**

```vb
SetLicense(15)
```

### ShowAuthor Function

This function is the heart of your protection and is responsible for popping up the protection dialog box. This function must be called at the end of your protection code block.

**Syntax:**

```vb  
Function ShowAuthor()
```

No parameters are required. 

**Example:**

```vb
ShowAuthor()
```

### NotLicensed 

The NotLicensed public variable indicates the state of your product license. It will be True if the protected product is registered or within the trial period. 

**Syntax:**

```vb
Public NotLicensed As Boolean = False 
```

**Example:**

```vb 
Dim MyProtection As New DynamicComponents.AppProtector()

If MyProtection.NotLicensed Then Exit Sub
```

### Activation Key Utility

Using the Activation Key utility you can generate huge numbers of randomized activation keys based on the algorithms you use. So the activation keys collection generated by SetAlgorithms(1234,56,78) will differ completely from one generated using SetAlgorithms(1111,11,11) or any other algorithms.

**Example:** 

Here are some activation keys generated using the algorithms:

SetAlgorithms(1234,56,78)  

2533-177-552-708-7856    
2670-209-627-395-7963    
2858-259-683-679-4606    
3210-373-873-517-1567    
3331-419-780-812-0071    
2412-152-129-710-8440    
3451-468-894-209-3279    
2222-117-365-198-8042    
3193-367-706-720-5254    
2616-196-555-752-0925    

SetAlgorithms(1111,11,11)

2167-115-069-275-1206
2933-292-542-319-1226   
3781-640-481-975-8749
3784-642-049-096-4889
3797-648-869-680-0506
3767-633-202-668-7204
3607-553-914-590-1600  
2381-153-727-457-2744
3923-717-512-323-8126   
3805-653-091-025-3862

There are 50 million encrypted algorithms available generated from any combination of (****, **, **) where:

- The first algorithm must be between 1000 and 7000 ==> (7000 - 1000) ==> 6000 options
- The second algorithm must be between 10 and 90 ==> (90 - 10) ==> 80 options   
- The third algorithm must be between 10 and 90 ==> (90 - 10) ==> 80 options

This is (6000 * 80 * 80) ==> 4,800,000 different combinations

## Tutorial

This tutorial describes all the features supported by DC.AppProtector. 

You can also refer to the project example installed by default at: 

C:\Program Files\Dynamic Components\Application Protector\Tutorial\

This code must be in the first form loaded in your project:

```vb
Private Sub TestForm_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load

  Dim MyProtection As New DynamicComponents.AppProtector()
  
  Dim ProductName As String
  
  Dim CompanyInfo As String

  ' Customized author message
  
  CompanyInfo = "Company Name: EgyFirst Software, inc." + vbCrLf ' vbCrLf forces a new line
  
  CompanyInfo += "Home Page: http://www.egyfirst.com" + vbCrLf
  
  CompanyInfo += "License: Free 30 Days Trial Version"

  ProductName = "DC AppProtector v1.0"

  ' Code of Protection

  MyProtection.SetInformation(ProductName, CompanyInfo, "http://www.egyfirst.com/buy")

  MyProtection.SetAlgorithms(1234, 56, 78)
  
  MyProtection.SetLicense(30) ' Default is 30 days
  
  MyProtection.ShowAuthor()

End Sub
```
