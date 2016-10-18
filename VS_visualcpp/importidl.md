---
title: "importidl"
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
ms.topic: language-reference
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
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
# importidl
Inserts the specified .idl file into the generated .idl file.  
  
## Syntax  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### Parameters  
 `idl_file`  
 Identifies the name of the .idl file that you want to merge with the .idl file that will be generated for your application.  
  
## Remarks  
 The **importidl** C++ attribute places the section outside of the library block (in `idl_file`) into your program's generated .idl file and the library section (in `idl_file`) into the library section of your program's generated .idl file.  
  
 You may want to use **importidl**, for example, if you want to use a hand-coded .idl file with your generated .idl file.  
  
## Example  
  
```  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
```  
  
## Requirements  
  
### Attribute Context  
  
|||  
|-|-|  
|**Applies to**|Anywhere|  
|**Repeatable**|No|  
|**Required attributes**|None|  
|**Invalid attributes**|None|  
  
 For more information, see [Attribute Contexts](../VS_visualcpp/Attribute-Contexts.md).  
  
## See Also  
 [Compiler Attributes](../VS_visualcpp/Compiler-Attributes.md)   
 [Stand-Alone Attributes](../VS_visualcpp/Stand-Alone-Attributes.md)   
 [import](../VS_visualcpp/import.md)   
 [importlib](../VS_visualcpp/importlib.md)   
 [include](../VS_visualcpp/include--C---.md)   
 [includelib](../VS_visualcpp/includelib--C---.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)