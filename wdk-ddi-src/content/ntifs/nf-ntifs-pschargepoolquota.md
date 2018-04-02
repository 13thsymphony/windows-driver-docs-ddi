---
UID: NF:ntifs.PsChargePoolQuota
title: PsChargePoolQuota function
author: windows-driver-content
description: The PsChargePoolQuota routine charges pool quota of the specified pool type to the specified process.
old-location: ifsk\pschargepoolquota.htm
old-project: ifsk
ms.assetid: c405771c-726f-4003-b3c6-f063dd74187e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PsChargePoolQuota, PsChargePoolQuota routine [Installable File System Drivers], ifsk.pschargepoolquota, ntifs/PsChargePoolQuota, psref_690f1550-4753-4f39-bcf2-bdcf7b80112d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsChargePoolQuota
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# PsChargePoolQuota function
The <b>PsChargePoolQuota</b> routine charges pool quota of the specified pool type to the specified process.

## Syntax

```
NTKERNELAPI VOID PsChargePoolQuota(
  PEPROCESS Process,
  POOL_TYPE PoolType,
  ULONG_PTR Amount
);
```

## Parameters

`Process`

Pointer to the process whose quota is to be charged.

`PoolType`

Type of pool quota to charge, which can be one of the following: 

<ul>
<li><b>NonPagedPool</b></li>
<li><b>PagedPool</b></li>
<li><b>NonPagedPoolCacheAligned</b></li>
<li><b>PagedPoolCacheAligned</b></li>
</ul>


<b>Note</b>: The <b>NonPagedPoolMustSucceed</b> and <b>NonPagedPoolCacheAlignedMustS</b> pool types are obsolete and should no longer be used.

`Amount`

Number of bytes to charge against the pool quota for this process.


## Return Value

None

## Remarks

If insufficient quota exists for the process, quota is not charged, and <b>PsChargePoolQuota</b> raises an exception with the status value STATUS_QUOTA_EXCEEDED. Callers are responsible for handling this exception. Thus calls to <b>PsChargePoolQuota</b> must be wrapped within a driver-supplied exception handler.

Every successful call to <b>PsChargePoolQuota</b> must be matched by a subsequent call to <b>PsReturnPoolQuota</b>.

For more information about memory management, see <a href="https://msdn.microsoft.com/e030a37c-26ab-4177-9980-4336928975e1">Memory Management</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551936">PsReturnPoolQuota</a>