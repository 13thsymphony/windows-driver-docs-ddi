---
UID: NF:wdm.WRITE_REGISTER_USHORT
title: WRITE_REGISTER_USHORT function
author: windows-driver-content
description: The WRITE_REGISTER_USHORT routine writes a USHORT value to the specified address.
old-location: kernel\write_register_ushort.htm
old-project: kernel
ms.assetid: ebcbec0c-c5ee-4af1-be3c-36c730f82f4e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: WRITE_REGISTER_USHORT, WRITE_REGISTER_USHORT routine [Kernel-Mode Driver Architecture], k103_bc20d667-b3c7-4e46-a21d-06123e73d348.xml, kernel.write_register_ushort, wdm/WRITE_REGISTER_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
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
-	WRITE_REGISTER_USHORT
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# WRITE_REGISTER_USHORT function
The <b>WRITE_REGISTER_USHORT</b> routine writes a USHORT value to the specified address.

## Syntax

````
VOID WRITE_REGISTER_USHORT(
  _In_ PUSHORT Register,
  _In_ USHORT  Value
);
````

## Parameters

`Register`

Pointer to the register, which must be a mapped range in memory space.

`Value`

Specifies a USHORT value to be written to the register.


## Return Value

None

## Remarks

Callers of <b>WRITE_REGISTER_USHORT</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h, Wudfwdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (see Remarks section) |