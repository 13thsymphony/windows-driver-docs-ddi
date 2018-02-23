---
UID: NF:printoem.OEMGetInfo
title: OEMGetInfo function
author: windows-driver-content
description: OEMGetInfo function
old-location: print\oemgetinfo.htm
old-project: print
ms.assetid: 69df63ac-2468-49d3-87ac-1930b718dddf
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.oemgetinfo, OEMGetInfo function [Print Devices], printoem/OEMGetInfo, print_obsoletefunctions_d9641912-6a33-4d32-979c-be21eb0e42cf.xml, OEMGetInfo
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
-	OEMGetInfo
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMGetInfo function


## Syntax

````
BOOL APIENTRY OEMGetInfo(
        DWORD                        dwMode,
  _Out_ _writes_bytes_(cbSize) PVOID pBuffer,
        DWORD                        cbSize,
  _Out_ DWORD                        pcbNeeded
);
````

## Parameters

`dwMode`



`pBuffer`



`cbSize`



`pcbNeeded`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |