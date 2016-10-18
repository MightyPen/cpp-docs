---
title: "Commands and Tables"
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
  - "OLE DB consumer templates, table support"
  - "CCommand class, OLE DB consumer templates"
  - "commands [C++], OLE DB Consumer Templates"
  - "CTable class"
  - "CAccessorRowset class, command and table classes"
  - "rowsets, accessing"
  - "tables [C++], OLE DB Consumer Templates"
  - "OLE DB consumer templates, command support"
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
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
# Commands and Tables
Commands and tables allow you to access rowsets; that is, open rowsets, execute commands, and bind columns. The [CCommand](../data/ccommand-class.md) and [CTable](../data/ctable-class.md) classes instantiate the command and table objects, respectively. These classes derive from [CAccessorRowset](../data/caccessorrowset-class.md) as shown in the following figure.  
  
 ![CCommand and CTable](../data/media/vccommandstables.gif "vcCommandsTables")  
Command and Table Classes  
  
 In the previous table, `TAccessor` can be any accessor type listed in [Accessor Types](../data/accessors-and-rowsets.md). *TRowset* can be any rowset type listed in [Rowset Types](../data/accessors-and-rowsets.md). *TMultiple* specifies the result type (a single or multiple result set).  
  
 The [ATL OLE DB Consumer Wizard](../atl/atl-ole-db-consumer-wizard.md) lets you specify whether you want a command or table object.  
  
-   For data sources without commands, you can use the `CTable` class. You generally use it for simple rowsets that specify no parameters and require no multiple results. This simple class opens a table on a data source using a table name that you specify.  
  
-   For data sources that support commands, you can use the `CCommand` class instead. To execute a command, call [Open](../data/ccommand--open.md) on this class. As an alternative, you can call `Prepare` to prepare a command that you want to execute more than once.  
  
     **CCommand** has three template arguments: an accessor type, a rowset type, and a result type (`CNoMultipleResults`, by default, or `CMultipleResults`). If you specify `CMultipleResults`, the `CCommand` class supports the **IMultipleResults** interface and handles multiple rowsets. The [DBVIEWER](assetId:///07620f99-c347-4d09-9ebc-2459e8049832) sample shows how to handle the multiple results.  
  
## See Also  
 [OLE DB Consumer Templates](../data/ole-db-consumer-templates--c---.md)