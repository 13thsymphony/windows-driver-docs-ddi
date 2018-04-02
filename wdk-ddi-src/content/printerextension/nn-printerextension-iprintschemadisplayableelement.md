---
UID: NN:printerextension.IPrintSchemaDisplayableElement
title: IPrintSchemaDisplayableElement
author: windows-driver-content
description: Provides the displayable string for a PrintCapabilites PrintSchema element.
old-location: print\iprintschemadisplayableelement_interface.htm
old-project: print
ms.assetid: A1ACF7C4-2DEE-405E-AEEE-BC03B9D5FAD2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaDisplayableElement, IPrintSchemaDisplayableElement interface [Print Devices], IPrintSchemaDisplayableElement interface [Print Devices], described, print.iprintschemadisplayableelement_interface, printerextension/IPrintSchemaDisplayableElement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaDisplayableElement
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaDisplayableElement interface

Provides the displayable string for a PrintCapabilites PrintSchema element.

## Methods

<p>The <b>IPrintSchemaDisplayableElement</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [IPrintSchemaDisplayableElement::get_DisplayName](nf-printerextension-iprintschemadisplayableelement-get_displayname.md) | Gets a displayable string for this item. |


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451270">IPrintSchemaElement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn465890">IPrintSchemaParameterDefinition</a>