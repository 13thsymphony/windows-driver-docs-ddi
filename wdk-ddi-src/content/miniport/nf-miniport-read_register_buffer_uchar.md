---
UID: NF:miniport.READ_REGISTER_BUFFER_UCHAR
title: READ_REGISTER_BUFFER_UCHAR function
author: windows-driver-content
description: The READ_REGISTER_BUFFER_UCHAR routine reads a number of bytes from the specified register address into a buffer.
old-location: kernel\read_register_buffer_uchar.htm
old-project: kernel
ms.assetid: 4ce9f377-ca5e-4574-9d80-60b74ee0de85
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: READ_REGISTER_BUFFER_UCHAR, k103_053aab44-4a1f-4eb3-a052-ee00f16a349d.xml, READ_REGISTER_BUFFER_UCHAR routine [Kernel-Mode Driver Architecture], wdm/READ_REGISTER_BUFFER_UCHAR, kernel.read_register_buffer_uchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h, Wudfwdm.h
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
-	READ_REGISTER_BUFFER_UCHAR
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---


# READ_REGISTER_BUFFER_UCHAR function
The <b>READ_REGISTER_BUFFER_UCHAR</b> routine reads a number of bytes from the specified register address into a buffer.

## Syntax

````
VOID READ_REGISTER_BUFFER_UCHAR(
  _In_  PUCHAR Register,
  _Out_ PUCHAR Buffer,
  _In_  ULONG  Count
);
````

## Parameters

`Register`

Pointer to the register, which must be a mapped range in memory space.

`Buffer`

Pointer to a buffer into which an array of UCHAR values is read.

`Count`

Specifies the number of bytes to be read into the buffer.


## Return Value

None

## Remarks

The size of the buffer must be large enough to contain at least the specified number of bytes.

Callers of <b>READ_REGISTER_BUFFER_UCHAR</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Register</i> is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h, Wudfwdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (see Remarks section) |