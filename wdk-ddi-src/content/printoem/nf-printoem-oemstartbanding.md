---
UID: NF:printoem.OEMStartBanding
title: OEMStartBanding function
author: windows-driver-content
description: The OEMStartBanding function is called by GDI when it is ready to start sending bands of a physical page to the driver for rendering.
old-location: print\oemstartbanding.htm
old-project: print
ms.assetid: dc9a1cf4-89d5-46d4-b914-1bc8368d3a42
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.oemstartbanding, OEMStartBanding function [Print Devices], OEMStartBanding, print_unidrv-pscript_rendering_6738c42a-92b2-4360-ae4c-a4b474948667.xml, printoem/OEMStartBanding
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Printoem.h
apiname:
-	OEMStartBanding
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMStartBanding function
The <code>OEMStartBanding</code> function is called by GDI when it is ready to start sending bands of a physical page to the driver for rendering.

## Syntax

````
BOOL APIENTRY OEMStartBanding(
   SURFOBJ *pso,
   POINTL  *pptl
);
````

## Parameters

`pso`



`pptl`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |