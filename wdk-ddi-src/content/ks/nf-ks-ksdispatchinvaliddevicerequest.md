---
UID: NF:ks.KsDispatchInvalidDeviceRequest
title: KsDispatchInvalidDeviceRequest function
author: windows-driver-content
description: The KsDispatchInvalidDeviceRequest function is used in KSDISPATCH_TABLE entries that are not handled and that need to return STATUS_INVALID_DEVICE_REQUEST.
old-location: stream\ksdispatchinvaliddevicerequest.htm
old-project: stream
ms.assetid: 7c30bc5b-2bd5-4db9-acaf-0c0347035ae3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KsDispatchInvalidDeviceRequest, KsDispatchInvalidDeviceRequest function [Streaming Media Devices], ksfunc_9be97c86-7505-4192-8a61-8280fca7ba0c.xml, stream.ksdispatchinvaliddevicerequest, KsDispatchInvalidDeviceRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsDispatchInvalidDeviceRequest
product: Windows
targetos: Windows
req.typenames: 
---


# KsDispatchInvalidDeviceRequest function
The <b>KsDispatchInvalidDeviceRequest</b> function is used in KSDISPATCH_TABLE entries that are not handled and that need to return STATUS_INVALID_DEVICE_REQUEST.

## Syntax

````
NTSTATUS KsDispatchInvalidDeviceRequest(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````

## Parameters

`DeviceObject`

Specifies the device object associated with the IRP.

`Irp`

Specifies the IRP that is not being handled.


## Return Value

The <b>KsDispatchInvalidDeviceRequest</b> function returns STATUS_INVALID_DEVICE_REQUEST and completes the IRP.

## Remarks

The <b>KsDispatchInvalidDeviceRequest</b> function is needed because the dispatch table for an opened instance of a device may not handle a specific major function that another opened instance needs to handle. Therefore, the function pointer in the driver object must always point to a function that calls a dispatch table entry.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="..\ks\nf-ks-ksdispatchfastiodevicecontrolfailure.md">KsDispatchFastIoDeviceControlFailure</a>



<a href="..\ks\nf-ks-ksdispatchfastreadfailure.md">KsDispatchFastReadFailure</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561706">KsDispatchFastWriteFailure</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDispatchInvalidDeviceRequest function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>