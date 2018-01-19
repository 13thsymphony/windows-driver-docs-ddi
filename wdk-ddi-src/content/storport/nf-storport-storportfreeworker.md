---
UID : NF:storport.StorPortFreeWorker
title : StorPortFreeWorker function
author : windows-driver-content
description : Frees a Storport work item previously allocated by the StorPortInitializeWorker routine.
old-location : storage\storportfreeworker.htm
old-project : storage
ms.assetid : 90BD61C8-322B-48D5-83E0-7204E3DC4423
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortFreeWorker
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 8 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : StorPortFreeWorker
req.alt-loc : storport.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortFreeWorker function
Frees a Storport work item previously allocated by the <a href="..\storport\nf-storport-storportinitializeworker.md">StorPortInitializeWorker</a> routine.

## Syntax

````
ULONG StorPortFreeWorker(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID WorkItem
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`Worker`




## Return Value

The <a href="..\storport\nf-storport-storportinitializeworker.md">StorPortInitializeWorker</a> routine returns one of these status codes:
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>Current IRQL &gt; DISPATCH_LEVEL.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>Either <i>HwDeviceExtension</i> or <i>WorkItem</i> is NULL.
<dl>
<dt><b>STOR_STATUS_BUSY</b></dt>
</dl>The work item is currently queued for processing.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The work item was successfully freed.
<dl>
<dt><b>STOR_STATUS_UNSUCCESSFUL</b></dt>
</dl>The work item is already free.

## Remarks

Miniports should call <b>StorPortFreeWorker</b> whenever a work item is no longer needed or when the miniport receives a PnP SRB notification  that the adapter is removed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\storport\nf-storport-storportinitializeworker.md">StorPortInitializeWorker</a>
</dt>
<dt>
<a href="..\storport\nf-storport-storportqueueworkitem.md">StorPortQueueWorkItem</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortFreeWorker routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>