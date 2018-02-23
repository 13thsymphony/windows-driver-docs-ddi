---
UID: NF:miniport.READ_REGISTER_ULONG
title: READ_REGISTER_ULONG function
author: windows-driver-content
description: The READ_REGISTER_ULONG routine reads a ULONG value from the specified register address.
old-location: kernel\read_register_ulong.htm
old-project: kernel
ms.assetid: a462734c-cac6-4de0-95c1-810766ef1644
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.read_register_ulong, k103_c2da9866-18ac-438b-aa32-991d1bda139f.xml, READ_REGISTER_ULONG routine [Kernel-Mode Driver Architecture], wdm/READ_REGISTER_ULONG, READ_REGISTER_ULONG
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	READ_REGISTER_ULONG
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---


# READ_REGISTER_ULONG function
The <b>READ_REGISTER_ULONG</b> routine reads a ULONG value from the specified register address.

## Syntax

````
ULONG READ_REGISTER_ULONG(
  _In_ PULONG Register
);
````

## Parameters

`Register`




## Return Value

<b>READ_REGISTER_ULONG</b> returns the ULONG value read from the specified register address.

## Remarks

Callers of <b>READ_REGISTER_ULONG</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h, Wudfwdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (see Remarks section) |