---
UID : NF:storport.StorPortIssueDpc
title : StorPortIssueDpc function
author : windows-driver-content
description : The StorPortIssueDpc routine issues a deferred procedure call (DPC).
old-location : storage\storportissuedpc.htm
old-project : storage
ms.assetid : a0c46c51-f6c4-4609-9dba-b730f33c3ed6
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortIssueDpc, storport/StorPortIssueDpc, StorPortIssueDpc routine [Storage Devices], storprt_e9cbe677-4d21-4c07-97a2-9db50858321f.xml, storage.storportissuedpc
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : Storport.h
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortIssueDpc function
The <b>StorPortIssueDpc</b> routine issues a deferred procedure call (DPC).

## Syntax

````
BOOLEAN StorPortIssueDpc(
  _In_ PVOID     DeviceExtension,
  _In_ PSTOR_DPC Dpc,
  _In_ PVOID     SystemArgument1,
  _In_ PVOID     SystemArgument2
);
````

## Parameters

`DeviceExtension`

Pointer to the per-adapter device extension.

`Dpc`

Pointer to a buffer containing an initialized DPC object of type <a href="..\storport\ns-storport-_stor_dpc.md">STOR_DPC</a> returned by the <a href="..\storport\nf-storport-storportinitializedpc.md">StorPortInitializeDpc</a> routine.

`SystemArgument1`

Pointer to caller-supplied information that will be passed to the deferred routine.

`SystemArgument2`

Pointer to caller-supplied information that will be passed to the deferred routine.


## Return Value

The <b>StorPortIssueDpc</b> routine returns <b>TRUE</b> if the DPC was successfully inserted into the DPC queue, and <b>FALSE</b> otherwise.

## Remarks

The <b>StorPortIssueDpc</b>  routine calls the <a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a> kernel routine to queue the DPC. The <b>KeInsertQueueDpc</b> kernel routine does not allow a DPC to be queued multiple times. Thus, if the DPC object specified by the <i>Dpc</i> parameter is already in the DPC queue, <b>KeInsertQueueDpc</b> ignores the queue request. This ensures that a deferred routine initialized with <a href="..\storport\nf-storport-storportinitializedpc.md">StorPortInitializeDpc</a> is always synchronized with itself. In other words, the caller does not need to sequentialize calls to the <b>StorPortIssueDpc</b> routine to ensure that multiple instances the routine do not run simultaneously. 

If a miniport driver has multiple work-items that must be performed by the same DPC, the miniport driver must ensure that each work item completes before issuing the DPC for the next work item.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\storport\nf-storport-storportinitializedpc.md">StorPortInitializeDpc</a>

<a href="..\storport\ns-storport-_stor_dpc.md">STOR_DPC</a>

<a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortIssueDpc routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>