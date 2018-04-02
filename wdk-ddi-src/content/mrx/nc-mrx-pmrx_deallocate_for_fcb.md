---
UID: NC:mrx.PMRX_DEALLOCATE_FOR_FCB
title: PMRX_DEALLOCATE_FOR_FCB
author: windows-driver-content
description: The MRxDeallocateForFcb routine is called by RDBSS to request that the network mini-redirector deallocate an FCB structure. This call is in response to a request to close a file system object.
old-location: ifsk\mrxdeallocateforfcb.htm
old-project: ifsk
ms.assetid: 4347f481-cd8f-4a88-92e0-f6bc7a4b7ffb
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: MRxDeallocateForFcb, MRxDeallocateForFcb routine [Installable File System Drivers], PMRX_DEALLOCATE_FOR_FCB, ifsk.mrxdeallocateforfcb, mrx/MRxDeallocateForFcb, mrxref_02a9e4a3-db00-48e1-ac2e-cd6a47ae4c37.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: mrx.h
req.include-header: Mrx.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	mrx.h
api_name:
-	MRxDeallocateForFcb
product: Windows
targetos: Windows
req.typenames: SetDSMCounters_IN, *PSetDSMCounters_IN
---


# PMRX_DEALLOCATE_FOR_FCB callback function
The<i> MRxDeallocateForFcb</i> routine is called by <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-rdbss-driver-and-library">RDBSS</a> to request that the network mini-redirector deallocate an FCB structure. This call is in response to a request to close a file system object.

## Syntax

```
PMRX_DEALLOCATE_FOR_FCB PmrxDeallocateForFcb;

NTSTATUS PmrxDeallocateForFcb(
  IN OUT PMRX_FCB Fcb
)
{...}
```

## Parameters

`Fcb`




## Return Value

<i>MRxDeallocateForFcb</i> returns STATUS_SUCCESS.

## Remarks

<i>MRxDeallocateForFcb</i> is called by <a href="https://msdn.microsoft.com/library/windows/hardware/ff554412">RxFinalizeNetFCB</a> as part of the process to finalize an FCB structure. The calls to <b>RxFinalizeNetFCB</b> and <i>MRxDeallocateForFcb</i> occur when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550720">IRP_MJ_CLOSE</a> request is received.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mrx.h (include Mrx.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549838">MRxAreFilesAliased</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549841">MRxCleanupFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549845">MRxCloseSrvOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549847">MRxCollapseOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549862">MRxCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549872">MRxDeallocateForFobx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549878">MRxExtendForCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549879">MRxExtendForNonCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550669">MRxFlush</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550677">MRxForceClosed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550691">MRxIsLockRealizable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550817">MRxShouldTryToCollapseThisOpen</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550839">MRxTruncate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550844">MRxZeroExtend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554412">RxFinalizeNetFCB</a>