---
UID: NF:wdm.WRITE_REGISTER_ULONG
title: WRITE_REGISTER_ULONG function
author: windows-driver-content
description: The WRITE_REGISTER_ULONG routine writes a ULONG value to the specified address.
old-location: kernel\write_register_ulong.htm
old-project: kernel
ms.assetid: d1f3d510-5b2c-4956-b9e0-cd26b2d818a9
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k103_af58a3ec-4102-4a89-9c58-e56f99d793d0.xml, wdm/WRITE_REGISTER_ULONG, WRITE_REGISTER_ULONG routine [Kernel-Mode Driver Architecture], kernel.write_register_ulong, WRITE_REGISTER_ULONG
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	WRITE_REGISTER_ULONG
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# WRITE_REGISTER_ULONG function
The <b>WRITE_REGISTER_ULONG</b> routine writes a ULONG value to the specified address.

## Syntax

````
VOID WRITE_REGISTER_ULONG(
  _In_ PULONG Register,
  _In_ ULONG  Value
);
````

## Parameters

`Register`



`Value`




## Return Value

None

## Remarks

Callers of <b>WRITE_REGISTER_ULONG</b> can be running at any IRQL, assuming the <i>Register</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h, Wudfwdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (see Remarks section) |