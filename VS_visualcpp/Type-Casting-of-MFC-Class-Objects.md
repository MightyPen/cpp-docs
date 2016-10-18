---
title: "Type Casting of MFC Class Objects"
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
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 11
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
# Type Casting of MFC Class Objects
Type casting macros provide a way to cast a given pointer to a pointer that points to an object of specific class, with or without checking that the cast is legal.  
  
 The following table lists the MFC type casting macros.  
  
### Macros That Cast Pointers to MFC Class Objects  
  
|||  
|-|-|  
|[DYNAMIC_DOWNCAST](../Topic/DYNAMIC_DOWNCAST.md)|Casts a pointer to a pointer to a class object while checking to see if the cast is legal.|  
|[STATIC_DOWNCAST](../Topic/STATIC_DOWNCAST.md)|Casts a pointer to an object from one class to a pointer of a related type. In a debug build, causes an                             **ASSERT** if the object is not a "kind of" the target type.|  
  
##  <a name="dynamic_downcast"></a>  DYNAMIC_DOWNCAST  
 Provides a handy way to cast a pointer to a pointer to a class object while checking to see if the cast is legal.  
  
```  
  
DYNAMIC_DOWNCAST(  
class  
,   
pointer  
)  
  
```  
  
### Parameters  
 `class`  
 The name of a class.  
  
 `pointer`  
 A pointer to be cast to a pointer to an object of type                                 `class`.  
  
### Remarks  
 The macro will cast the                         `pointer` parameter to a pointer to an object of the                         `class` parameter's type.  
  
 If the object referenced by the pointer is a "kind of" the identified class, the macro returns the appropriate pointer. If it is not a legal cast, the macro returns                         **NULL**.  
  
##  <a name="static_downcast"></a>  STATIC_DOWNCAST  
 Casts                 *pobject* to a pointer to a                 *class_name* object.  
  
```  
  
STATIC_DOWNCAST(  
class_name  
,  
pobject  
)  
  
```  
  
### Parameters  
 *class_name*  
 The name of the class being cast to.  
  
 *pobject*  
 The pointer to be cast to a pointer to a                                 *class_name* object.  
  
### Remarks  
 *pobject* must either be                         **NULL**, or point to an object of a class which is derived directly, or indirectly, from                         *class_name*. In builds of your application with the                         **_DEBUG** preprocessor symbol defined, the macro will                         **ASSERT** if                         *pobject* is not                         **NULL**, or if it points to an object that is not a "kind of" the class specified in the                         *class_name* parameter (see                         [CObject::IsKindOf](../Topic/CObject::IsKindOf.md)). In non-                        **_DEBUG** builds, the macro performs the cast without any type checking.  
  
 The class specified in the                         *class_name* parameter must be derived from                         `CObject` and must use the                         `DECLARE_DYNAMIC` and                         `IMPLEMENT_DYNAMIC`, the                         `DECLARE_DYNCREATE` and                         `IMPLEMENT_DYNCREATE`, or the                         `DECLARE_SERIAL` and                         `IMPLEMENT_SERIAL` macros as explained in the article                         [CObject Class: Deriving a Class from CObject](../VS_visualcpp/Deriving-a-Class-from-CObject.md).  
  
 For example, you might cast a pointer to                         `CMyDoc`, called                         `pMyDoc`, to a pointer to                         **CDocument** using this expression:  
  
 [!CODE [NVC_MFCDocView#197](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#197)]  
  
 If                         `pMyDoc` does not point to an object derived directly or indirectly from                         **CDocument**, the macro will                         **ASSERT**.  
  
## See Also  
 [Macros and Globals](../VS_visualcpp/MFC-Macros-and-Globals.md)