---
UID: NE.printerextension.tagPrintSchemaSelectionType
title: tagPrintSchemaSelectionType
author: windows-driver-content
description: The PrintSchemaSelectionType enumeration identifies how a Feature’s options should be selected. This property appears only in a PrintCapabilities document.
old-location: print\printschemaselectiontype.htm
old-project: print
ms.assetid: 30BB7A95-512C-418B-B496-47832DD4C0BC
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: tagPrintSchemaSelectionType, PrintSchemaSelectionType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PrintSchemaSelectionType
req.alt-loc: Printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# tagPrintSchemaSelectionType enumeration



## -description
The PrintSchemaSelectionType enumeration identifies how a Feature’s options should be selected. This property appears only in a PrintCapabilities document. 


## -syntax

````
typedef enum tagPrintSchemaSelectionType { 
  PrintSchemaSelectionType_PickOne   = 0,
  PrintSchemaSelectionType_PickMany  = 1
} PrintSchemaSelectionType;
````


## -enum-fields

### -field PrintSchemaSelectionType_PickOne

Select one.

### -field PrintSchemaSelectionType_PickMany

Select many.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>