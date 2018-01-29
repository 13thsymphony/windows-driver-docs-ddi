---
UID : NF:ks.KsDispatchIrp
title : KsDispatchIrp function
author : windows-driver-content
description : KsDispatchIrp calls a dispatch routine corresponding to the function code of the specified IRP. KsDispatchIrp then returns the status code from this call.
old-location : stream\ksdispatchirp.htm
old-project : stream
ms.assetid : 6ee88b2d-4086-4e6d-b80b-eff6868ce784
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsDispatchIrp, stream.ksdispatchirp, ksfunc_ed03b195-fcb3-41ca-9794-c9b9f04ce8c9.xml, ks/KsDispatchIrp, KsDispatchIrp routine [Streaming Media Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
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
req.lib : Ks.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---


# KsDispatchIrp function
<b>KsDispatchIrp</b> calls a dispatch routine corresponding to the function code of the specified IRP. <b>KsDispatchIrp</b> then returns the status code from this call.

## Syntax

````
NTSTATUS KsDispatchIrp(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````

## Parameters

`DeviceObject`

Specifies a pointer to the <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> to which the specific file object belongs.

`Irp`

Contains the IRP for which to call a dispatch routine.


## Return Value

Returns the status code returned from the dispatch routine.

## Remarks

A <a href="..\ks\ns-ks-ksdispatch_table.md">KSDISPATCH_TABLE</a> can be contained in the stack location's file object's <b>FsContext</b> member. <b>KsDispatchIrp</b> calls the dispatch routine listed in this dispatch table for that major code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\ks\nf-ks-kssetmajorfunctionhandler.md">KsSetMajorFunctionHandler</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDispatchIrp routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>