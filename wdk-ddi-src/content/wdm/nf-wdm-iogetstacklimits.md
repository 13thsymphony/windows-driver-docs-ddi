---
UID : NF:wdm.IoGetStackLimits
title : IoGetStackLimits function
author : windows-driver-content
description : The IoGetStackLimits routine returns the boundaries of the current thread's stack frame.
old-location : kernel\iogetstacklimits.htm
old-project : kernel
ms.assetid : aaa10cb2-16cb-40a8-ad72-9715da311957
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : IoGetStackLimits
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IoGetStackLimits
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : See Remarks section.
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# IoGetStackLimits function
The <b>IoGetStackLimits</b> routine returns the boundaries of the current thread's stack frame.

## Syntax

````
VOID IoGetStackLimits(
  _Out_ PULONG_PTR LowLimit,
  _Out_ PULONG_PTR HighLimit
);
````

## Parameters

`LowLimit`

Pointer to a caller-supplied variable in which this routine returns the lower offset of the current thread's stack frame.

`HighLimit`

Pointer to a caller-supplied variable in which this routine returns the higher offset of the current thread's stack frame.


## Return Value

None

## Remarks

Highest-level drivers can call this routine, particularly file systems that have been passed a pointer to a location on the current thread's stack.

In Windows Server 2003 Service Pack 1 (SP1) and later versions of Windows, callers of <b>IoGetStackLimits</b> can be running at any IRQL. For earlier operating systems, the caller must be running at IRQL &lt;= APC_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-iogetinitialstack.md">IoGetInitialStack</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iogetremainingstacksize.md">IoGetRemainingStackSize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoGetStackLimits routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>