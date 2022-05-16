## **DynamicComponents - ReturnKeyEnable**

Powered by ![](images/Aspose.Words.73bbce01-875a-4fb9-be3b-af906f986d16.001.png)


## **Overview**

DC.ReturnKeyEnable is a COM based component that enables you navigate thriugh form controls using Retun key as with Tab Key

DC.ReturnKeyEnable may be used with any developing language support COM based application like Visual Basic,Visual C++,Borland C++,Delphi and others ..

EgyFirst has done a lot of work for you. no need to waste time , defining events to every control within your form to handle Return key press 
you design your form as usual and we allow you move through its controls as wanted
## **Features**
Only one line of code and you can move easily through your form controls without any additional programming 
**that is all !!**


**Example:**

RKE.[EnableReturnKey](##chmtopic8)(Me, True) //' Now you can use Return Key to move through contols insted of Tab Key
## **System Requirements**
DC.ReturnKeyEnable runs as a COM class for Developing with Visual Basic.Net underMicrosoft Windows 98/NT/ 2000 or Windows XP. 


## **Installing DC.ReturnKeyEnable**
The DC.ReturnKeyEnable setup program will automatically register theDC\_ReturnKeyEnable10.dll file on your system. 

There is no need to manually run RegSvr32.exe on your development system. 
## **Including DC.ReturnKeyEnable** 

To include DC.ReturnKeyEnable in your project 

1. From Project menu select add reference 
1. Push Browse button to locate your DC\_ReturnKeyEnable10.DLL file which by default located in [c:\windows\system32](file:///c:/windows/system32) , now the specific DLL included in your references


## **Deploying DC.ReturnKey Enable Applications**
The only file needs to be distributed withDC.ReturnKeyEnable COM applications is DC\_ReturnKeyEnable 10.dll

this file should be copied to the WinSystem directory which by default is C:\Windows\System32 
## **EnableReturnKey**
Enable you navigate through controls with Return key as with tab key

**Syntax:**

Function EnableReturnKey(ByVal Mode As Boolean)

**Example:**

RKE.EnableReturnKey(True)
## Tutorial

This tutorial describe most of features supported by DC.ReturnKeyEnable 

also you can refer to the project example which installed by default into C:\Program Files\Dynamic Components\ReturnKeyEnable\Tutorial\


```
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

RKE.EnableReturnKey(Me, True) //' Now you can use Return Key to move through contols insted of Tab Key

End Sub
```

