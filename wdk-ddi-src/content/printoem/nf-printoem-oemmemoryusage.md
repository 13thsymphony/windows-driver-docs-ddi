---
UID: NF:printoem.OEMMemoryUsage
title: OEMMemoryUsage function
author: windows-driver-content
description: The OEMMEMORYUSAGE structure is used as an input parameter to a rendering plug-in's IPrintOemUni::MemoryUsage method.
old-location: print\oemmemoryusage.htm
old-project: print
ms.assetid: a7a522b8-7aa2-45b6-9200-407471dca82f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , E, M, O, OEMMEMORYUSAGE, OEMMEMORYUSAGE structure [Print Devices], OEMMemoryUsage, POEMMEMORYUSAGE, POEMMEMORYUSAGE structure pointer [Print Devices], U, a, e, g, m, o, print.oemmemoryusage, print_unidrv-pscript_rendering_c6746c1c-f6c5-4acf-bcd3-bc1f69382dae.xml, printoem/OEMMEMORYUSAGE, printoem/POEMMEMORYUSAGE, r, s, y"
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
-	printoem.h
apiname:
-	OEMMEMORYUSAGE
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMMemoryUsage function
The OEMMEMORYUSAGE structure is used as an input parameter to a rendering plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554264">IPrintOemUni::MemoryUsage</a> method.

## Syntax

````
typedef struct {
  DWORD dwFixedMemoryUsage;
  DWORD dwPercentMemoryUsage;
  DWORD dwMaxBandSize;
} OEMMEMORYUSAGE, *POEMMEMORYUSAGE;
````

## Parameters

`pdevobj`



`pMemoryUsage`




## Return Value

None

## Remarks

The Unidrv driver uses the values in the <b>dwFixedMemoryUsage</b> and <b>dwPercentMemoryUsage</b> members of this structure to determine the optimum size for a GDI drawing surface, taking into account any memory requirements of a rendering plug-in's <b>IPrintOemUni::ImageProcessing</b> method. For more information about how these members are used, see the Remarks section in <a href="https://msdn.microsoft.com/library/windows/hardware/ff554264">IPrintOemUni::MemoryUsage</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554264">IPrintOemUni::MemoryUsage</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554261">IPrintOemUni::ImageProcessing</a>