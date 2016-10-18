---
title: "Accelerator Modifier Property"
ms.custom: na
ms.date: 10/07/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: 5
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
# Accelerator Modifier Property
The following are legal entries for the Modifier property in the accelerator table.  
  
|Value|Description|  
|-----------|-----------------|  
|**None**|User presses only the Key value. This is most effectively used with the ASCII/ANSI values 001 through 026, which is interpreted as ^A through ^Z (CTRL-A through CTRL-Z).|  
|**Alt**|User must press the ALT key before the Key value.|  
|**Ctrl**|User must press the CTRL key before the Key value. Not valid with ASCII Type.|  
|**Shift**|User must press the SHIFT key before the Key value.|  
|**Ctrl+Alt**|User must press the CTRL key and the ALT key before the Key value. Not valid with ASCII Type.|  
|**Ctrl+Shift**|User must press the CTRL key and the SHIFT key before the Key value. Not valid with ASCII Type.|  
|**Alt+Shift**|User must press the ALT key and the SHIFT key before the Key value. Not valid with ASCII Type.|  
|**Ctrl+Alt+Shift**|User must press CTRL, ALT, and SHIFT before the Key value. Not valid with ASCII Type.|  
  
## Requirements  
 Win32  
  
## See Also  
 [Setting Accelerator Properties](../VS_visualcpp/Setting-Accelerator-Properties.md)   
 [Accelerator Editor](../VS_visualcpp/Accelerator-Editor.md)