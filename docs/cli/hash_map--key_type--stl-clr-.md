---
title: "hash_map::key_type (STL-CLR)"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_map::key_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_type member [STL/CLR]"
ms.assetid: 1e7d0f40-03e0-4413-b652-1d9fe14f0f12
caps.latest.revision: 12
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# hash_map::key_type (STL/CLR)
The type of an ordering key.  
  
## Syntax  
  
```  
typedef Key key_type;  
```  
  
## Remarks  
 The type is a synonym for the template parameter `Key`.  
  
## Example  
  
```  
// cliext_hash_map_key_type.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]" using key_type   
    for (Myhash_map::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in key_type object   
        Myhash_map::key_type val = it->first;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## Requirements  
 **Header:** \<cliext/hash_map>  
  
 **Namespace:** cliext  
  
## See Also  
 [hash_map (STL/CLR)](../cli/hash_map--stl-clr-.md)   
 [hash_map::key_compare (STL/CLR)](../cli/hash_map--key_compare--stl-clr-.md)   
 [hash_map::mapped_type (STL/CLR)](../cli/hash_map--mapped_type--stl-clr-.md)   
 [hash_map::value_type (STL/CLR)](../cli/hash_map--value_type--stl-clr-.md)