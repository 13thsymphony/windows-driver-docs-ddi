---
UID: NF:printoem.OEMMemoryUsage
title: OEMMemoryUsage function
author: windows-driver-content
description: This function is obsolete for Windows XP and later.wcs
old-location: print\oemmemoryusage__function_.htm
old-project: print
ms.assetid: ae78fc9a-06a2-466f-875c-9c35aec13336
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMMemoryUsage, OEMMemoryUsage function [Print Devices], print.oemmemoryusage__function_, print_obsoletefunctions_35165216-4a29-4096-95b6-5f5b00418193.xml, printoem/OEMMemoryUsage
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
-	OEMMemoryUsage
product:
- Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMMemoryUsage function
This function is obsolete for Windows XP and later.wcs

## Syntax

```
void OEMMemoryUsage(
  PDEVOBJ         pdevobj,
  POEMMEMORYUSAGE pMemoryUsage
);
```

## Parameters

`pdevobj`



`pMemoryUsage`




## Return Value

This function does not return a value.

<h2><a id="ddk_oemmemoryusage_function__gg"></a><a id="DDK_OEMMEMORYUSAGE_FUNCTION__GG"></a></h2>
This function is obsolete for Windows XP and later. It is supported only for earlier Unidrv plug-ins. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff554264">IPrintOemUni::MemoryUsage</a> instead.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |