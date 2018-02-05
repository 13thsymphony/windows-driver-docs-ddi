---
UID : NF:ntifs.PsReturnPoolQuota
title : PsReturnPoolQuota function
author : windows-driver-content
description : The PsReturnPoolQuota routine returns pool quota of the specified pool type to the specified process.
old-location : ifsk\psreturnpoolquota.htm
old-project : ifsk
ms.assetid : 12ceb592-97ca-41c9-89d0-26fd2dc87981
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PsReturnPoolQuota, PsReturnPoolQuota routine [Installable File System Drivers], ifsk.psreturnpoolquota, psref_7dc67879-8f0e-41a1-96cf-018dcf60afcd.xml, ntifs/PsReturnPoolQuota
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : "< DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# PsReturnPoolQuota function
The <b>PsReturnPoolQuota</b> routine returns pool quota of the specified pool type to the specified process.

## Syntax

````
VOID PsReturnPoolQuota(
  _In_ PEPROCESS Process,
  _In_ POOL_TYPE PoolType,
  _In_ ULONG_PTR Amount
);
````

## Parameters

`Process`

Pointer to the process whose quota is to be returned.

`PoolType`

Type of pool quota to return, which can be one of the following: 
<ul>
<li><b>NonPagedPool</b></li>
<li><b>PagedPool</b></li>
<li><b>NonPagedPoolCacheAligned</b></li>
<li><b>PagedPoolCacheAligned</b></li>
</ul>

<b>Note</b>: The <b>NonPagedPoolMustSucceed</b> and <b>NonPagedPoolCacheAlignedMustS</b> pool types are obsolete and should no longer be used.

`Amount`

Number of bytes to return to the pool quota for this process.


## Return Value

None

## Remarks

If the quota return would exceed the quota for the process, <b>PsReturnPoolQuota</b> raises an exception with the status value STATUS_QUOTA_EXCEEDED. Callers are responsible for handling this exception. Thus calls to <b>PsReturnPoolQuota</b> must be wrapped within a driver-supplied exception handler.

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

<a href="..\ntifs\nf-ntifs-pschargepoolquota.md">PsChargePoolQuota</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsReturnPoolQuota routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>