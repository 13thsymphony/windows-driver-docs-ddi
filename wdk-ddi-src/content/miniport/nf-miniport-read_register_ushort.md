---
UID: NF:miniport.READ_REGISTER_USHORT
title: READ_REGISTER_USHORT function
author: windows-driver-content
description: The READ_REGISTER_USHORT routine reads a USHORT value from the specified register address.
old-location: kernel\read_register_ushort.htm
old-project: kernel
ms.assetid: d1160b0a-9969-44ba-82e7-14048e1554c2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: READ_REGISTER_USHORT, READ_REGISTER_USHORT routine [Kernel-Mode Driver Architecture], k103_c2fa06bd-05b9-4fbd-b47c-f264d3ed0bd7.xml, kernel.read_register_ushort, wdm/READ_REGISTER_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h, Wudfwdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	READ_REGISTER_USHORT
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---


# READ_REGISTER_USHORT function
The <b>READ_REGISTER_USHORT</b> routine reads a USHORT value from the specified register address.

## Syntax

```
USHORT READ_REGISTER_USHORT(
  USHORT *Register
);
```

## Parameters

`Register`




## Return Value

<b>READ_REGISTER_USHORT</b> returns the USHORT value read from the specified register address.

## Remarks

Callers of <b>READ_REGISTER_USHORT</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h, Wudfwdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (see Remarks section) |