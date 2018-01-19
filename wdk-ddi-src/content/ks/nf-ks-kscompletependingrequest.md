---
UID : NF:ks.KsCompletePendingRequest
title : KsCompletePendingRequest function
author : windows-driver-content
description : The KsCompletePendingRequest function is used to complete an I/O request in response to which an AVStream dispatch function previously returned STATUS_PENDING.
old-location : stream\kscompletependingrequest.htm
old-project : stream
ms.assetid : 9bde557e-0759-4f5b-989e-a34a701d2ebd
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsCompletePendingRequest
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsCompletePendingRequest
req.alt-loc : Ks.lib,Ks.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : 
---


# KsCompletePendingRequest function
The<b> KsCompletePendingRequest</b> function is used to complete an I/O request in response to which an AVStream dispatch function previously returned STATUS_PENDING.

## Syntax

````
void KsCompletePendingRequest(
  _In_ PIRP Irp
);
````

## Parameters

`Irp`

A pointer to the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure that must be completed; this is passed in the dispatch function that returned a STATUS_PENDING.


## Return Value

None

## Remarks

If the dispatch function in question does not pass an IRP, it <b>cannot</b> return STATUS_PENDING. Minidrivers should set <b>IRP.IoStatus.Status</b> before calling this function.

<b>KsCompletePendingRequest</b> can be used for PnP dispatch functions in the device dispatch table or filter creation and closure requests. Dispatch functions that return STATUS_PENDING must call this function when they complete the request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\ns-ks-_ksdevice_dispatch.md">KSDEVICE_DISPATCH</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksfilter_dispatch.md">KSFILTER_DISPATCH</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_irp.md">IRP</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCompletePendingRequest function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>