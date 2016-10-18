---
title: "Type arguments inferred for method &#39;&lt;procedurename&gt;&#39; result in the following errors :&lt;errorlist&gt;"
ms.custom: na
ms.date: "10/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc30954"
  - "vbc30954"
helpviewer_keywords: 
  - "BC30954"
ms.assetid: 796592c4-70b7-45be-9322-db09e9095d7d
caps.latest.revision: 6
ms.author: "billchi"
manager: "douge"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Type arguments inferred for method &#39;&lt;procedurename&gt;&#39; result in the following errors :&lt;errorlist&gt;
A generic procedure is called without supplying any type arguments, and the inferred type arguments result in one or more constraint violations.  
  
 Normally, when you invoke a generic type, you supply a type argument for each type parameter the generic type defines. If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters. If the inferred types fail to satisfy one or more of the type parameter constraints, the compiler generates this error.  
  
 A *constraint* on a type parameter limits what type arguments can be passed to it. For example, a type parameter might be constrained to be a class that implements the \<xref:System.IComparable`1> interface. For more information, see "Constraints" in [Generic Procedures in Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md).  
  
 **Error ID:** BC30954  
  
### To correct this error  
  
-   Supply type arguments to the generic procedure so that the compiler does not have to infer them.  
  
## See Also  
 [Generic Types in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Generic Procedures in Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)