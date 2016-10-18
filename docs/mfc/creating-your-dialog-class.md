---
title: "Creating Your Dialog Class"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dialog boxes [C++], creating"
  - "MFC dialog boxes, creating"
  - "files [C++], creating"
  - "dialog classes, Add Class Wizard"
  - "dialog classes, creating"
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
caps.latest.revision: 7
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
# Creating Your Dialog Class
For each dialog box in your program, create a new dialog class to work with the dialog resource.  
  
 [Adding a Class](../ide/adding-a-class--visual-c---.md) explains how to create a new dialog class. When you create a dialog class with the Add Class Wizard, it writes the following items in the .H and .CPP files you specify:  
  
 In the .H file:  
  
-   A class declaration for the dialog class. The class is derived from [CDialog](../mfcref/cdialog-class.md).  
  
 In the .CPP file:  
  
-   A message map for the class.  
  
-   A standard constructor for the dialog box.  
  
-   An override of the [DoDataExchange](../Topic/CWnd::DoDataExchange.md) member function. Edit this function. It is used for dialog data exchange and validation capabilities as described later in [Dialog data exchange and validation](../mfc/dialog-data-exchange-and-validation.md).  
  
## See Also  
 [Creating a Dialog Class with Code Wizards](../mfc/creating-a-dialog-class-with-code-wizards.md)   
 [Life Cycle of a Dialog Box](../mfc/life-cycle-of-a-dialog-box.md)