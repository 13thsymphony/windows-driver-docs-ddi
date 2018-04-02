---
UID: NF:printoem.OEMEndDoc
title: OEMEndDoc function
author: windows-driver-content
description: The OEMEndDoc function is called by the GDI when it has finished sending a document to the driver for rendering.
old-location: print\oemenddoc.htm
old-project: print
ms.assetid: 268a22ba-1dce-4326-bdf4-4d7e7e83257c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMEndDoc, OEMEndDoc function [Print Devices], print.oemenddoc, print_unidrv-pscript_rendering_1b17db2b-0ea4-4acb-9130-bbc7fe3a0b4a.xml, printoem/OEMEndDoc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	OEMEndDoc
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMEndDoc function
The <code>OEMEndDoc</code> function is called by the GDI when it has finished sending a document to the driver for rendering.

## Syntax

```
BOOL OEMEndDoc(
  SURFOBJ *pso,
  FLONG   fl
);
```

## Parameters

`pso`



`fl`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |