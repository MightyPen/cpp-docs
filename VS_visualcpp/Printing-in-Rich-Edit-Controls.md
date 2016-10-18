---
title: "Printing in Rich Edit Controls"
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
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
caps.latest.revision: 8
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
# Printing in Rich Edit Controls
You can tell a rich edit control ([CRichEditCtrl](../VS_visualcpp/CRichEditCtrl-Class.md)) to render its output for a specified device, such as a printer. You can also specify the output device for which a rich edit control formats its text.  
  
 To format part of the contents of a rich edit control for a specific device, you can use the [FormatRange](../Topic/CRichEditCtrl::FormatRange.md) member function. The [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) structure used with this function specifies the range of text to format as well as the device context (DC) for the target device.  
  
 After formatting text for an output device, you can send the output to the device by using the [DisplayBand](../Topic/CRichEditCtrl::DisplayBand.md) member function. By repeatedly using `FormatRange` and `DisplayBand`, an application that prints the contents of a rich edit control can implement banding. (Banding is division of output into smaller parts for printing purposes.)  
  
 You can use the [SetTargetDevice](../Topic/CRichEditCtrl::SetTargetDevice.md) member function to specify the target device for which a rich edit control formats its text. This function is useful for WYSIWYG (what you see is what you get) formatting, in which an application positions text using the default printer's font metrics instead of the screen's.  
  
## See Also  
 [Using CRichEditCtrl](../VS_visualcpp/Using-CRichEditCtrl.md)   
 [Controls](../VS_visualcpp/Controls--MFC-.md)