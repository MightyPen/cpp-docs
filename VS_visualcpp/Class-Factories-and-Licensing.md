---
title: "Class Factories and Licensing"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 10
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# Class Factories and Licensing
To create an instance of your OLE control, a container application calls a member function of the control's class factory. Because your control is an actual OLE object, the class factory is responsible for creating instances of your control. Every OLE control class must have a class factory.  
  
 Another important feature of OLE controls is their ability to enforce a license. ControlWizard allows you to incorporate licensing during the creation of your control project. For more information on control licensing, see the article             [ActiveX Controls: Licensing An ActiveX Control](../VS_visualcpp/MFC-ActiveX-Controls--Licensing-an-ActiveX-Control.md).  
  
 The following table lists several macros and functions used to declare and implement your control's class factory and to license of your control.  
  
### Class Factories and Licensing  
  
|||  
|-|-|  
|[DECLARE_OLECREATE_EX](../Topic/DECLARE_OLECREATE_EX.md)|Declares the class factory for an OLE control or property page.|  
|[IMPLEMENT_OLECREATE_EX](../Topic/IMPLEMENT_OLECREATE_EX.md)|Implements the control's                             `GetClassID` function and declares an instance of the class factory.|  
|[BEGIN_OLEFACTORY](../Topic/BEGIN_OLEFACTORY.md)|Begins the declaration of any licensing functions.|  
|[END_OLEFACTORY](../Topic/END_OLEFACTORY.md)|Ends the declaration of any licensing functions.|  
|[AfxVerifyLicFile](../Topic/AfxVerifyLicFile.md)|Verifies whether a control is licensed for use on a particular computer.|  
  
##  <a name="declare_olecreate_ex"></a>  DECLARE_OLECREATE_EX  
 Declares a class factory and the                 `GetClassID` member function of your control class.  
  
```  
  
DECLARE_OLECREATE_EX(  
class_name  
)  
  
```  
  
### Parameters  
 *class_name*  
 The name of the control class.  
  
### Remarks  
 Use this macro in the control class header file for a control that does not support licensing.  
  
 Note that this macro serves the same purpose as the following code sample:  
  
 [!CODE [NVC_MFCAxCtl#14](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCAxCtl#14)]  
  
##  <a name="implement_olecreate_ex"></a>  IMPLEMENT_OLECREATE_EX  
 Implements your control's class factory and the                 [GetClassID](../Topic/COleControl::GetClassID.md) member function of your control class.  
  
```  
  
IMPLEMENT_OLECREATE_EX(  
class_name  
,   
external_name  
,   
l  
,   
w1  
,   
w2  
,   
b1  
,   
b2  
,   
b3  
,   
b4  
,   
b5  
,   
b6  
,   
b7  
,   
b8  
)  
  
```  
  
### Parameters  
 *class_name*  
 The name of the control property page class.  
  
 *external_name*  
 The object name exposed to applications.  
  
 *l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*  
 Components of the class's                                 **CLSID**. For more information on these parameters, see the Remarks for                                 [IMPLEMENT_OLECREATE](../Topic/IMPLEMENT_OLECREATE.md).  
  
### Remarks  
 This macro must appear in the implementation file for any control class that uses the                         `DECLARE_OLECREATE_EX` macro or the                         `BEGIN_OLEFACTORY` and                         `END_OLEFACTORY` macros. The external name is the identifier of the OLE control that is exposed to other applications. Containers use this name to request an object of this control class.  
  
##  <a name="begin_olefactory"></a>  BEGIN_OLEFACTORY  
 Begins the declaration of your class factory in the header file of your control class.  
  
```  
  
BEGIN_OLEFACTORY(  
class_name  
)  
  
```  
  
### Parameters  
 *class_name*  
 Specifies the name of the control class whose class factory this is.  
  
### Remarks  
 Declarations of class factory licensing functions should begin immediately after                         `BEGIN_OLEFACTORY`.  
  
##  <a name="end_olefactory"></a>  END_OLEFACTORY  
 Ends the declaration of your control's class factory.  
  
```  
  
END_OLEFACTORY(  
class_name  
)  
  
```  
  
### Parameters  
 *class_name*  
 The name of the control class whose class factory this is.  
  
##  <a name="afxverifylicfile"></a>  AfxVerifyLicFile  
 Call this function to verify that the license file named by                 `pszLicFileName` is valid for the OLE control.  
  
```  
  
BOOL  
AFXAPI  
AfxVerifyLicFile(  
   HINSTANCE  
hInstance  
,  
   LPCTSTR  
pszLicFileName  
,  
   LPOLESTR  
pszLicFileContents  
,  
   UINT  
cch  
=  
-1  
);  
  
```  
  
### Parameters  
 `hInstance`  
 The instance handle of the DLL associated with the licensed control.  
  
 `pszLicFileName`  
 Points to a null-terminated character string containing the license filename.  
  
 `pszLicFileContents`  
 Points to a byte sequence that must match the sequence found at the beginning of the license file.  
  
 `cch`  
 Number of characters in                                 `pszLicFileContents`.  
  
### Return Value  
 Nonzero if the license file exists and begins with the character sequence in                         `pszLicFileContents`; otherwise 0.  
  
### Remarks  
 If                         `cch` is – 1, this function uses:  
  
 [!CODE [NVC_MFC_Utilities#36](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_Utilities#36)]  
  
## See Also  
 [Macros and Globals](../VS_visualcpp/MFC-Macros-and-Globals.md)