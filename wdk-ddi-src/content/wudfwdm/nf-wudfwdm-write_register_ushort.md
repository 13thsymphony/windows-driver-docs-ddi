---
UID: NF:wudfwdm.WRITE_REGISTER_USHORT
title: WRITE_REGISTER_USHORT function
author: windows-driver-content
description: The WRITE_REGISTER_USHORT routine writes a USHORT value to the specified address.
old-location: kernel\write_register_ushort.htm
old-project: kernel
ms.assetid: ebcbec0c-c5ee-4af1-be3c-36c730f82f4e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WRITE_REGISTER_USHORT, WRITE_REGISTER_USHORT routine [Kernel-Mode Driver Architecture], wdm/WRITE_REGISTER_USHORT, kernel.write_register_ushort, k103_bc20d667-b3c7-4e46-a21d-06123e73d348.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfwdm.h
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
-	WRITE_REGISTER_USHORT
product: Windows
targetos: Windows
req.typenames: "*PPO_FX_PERF_STATE_UNIT, PO_FX_PERF_STATE_UNIT"
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



`Value`




## Return Value

None

## Remarks

Callers of <b>WRITE_REGISTER_USHORT</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wudfwdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h, Wudfwdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (see Remarks section) |