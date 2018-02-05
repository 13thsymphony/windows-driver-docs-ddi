---
UID : NF:portcls.IDrmPort2.ForwardContentToDeviceObject
title : IDrmPort2::ForwardContentToDeviceObject method
author : windows-driver-content
description : The ForwardContentToDeviceObject method accepts a device object representing a device to which the caller intends to forward protected content.
old-location : audio\idrmport2_forwardcontenttodeviceobject.htm
old-project : audio
ms.assetid : 4e5c8942-3ce2-40d8-8cd7-436a5ebbc8ee
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : ForwardContentToDeviceObject method [Audio Devices], IDrmPort2 interface, audio.idrmport2_forwardcontenttodeviceobject, IDrmPort2 interface [Audio Devices], ForwardContentToDeviceObject method, audmp-routines_6a59757e-e53e-4edb-aaa3-7dc695a1bc16.xml, IDrmPort2, portcls/IDrmPort2::ForwardContentToDeviceObject, ForwardContentToDeviceObject method [Audio Devices], ForwardContentToDeviceObject, IDrmPort2::ForwardContentToDeviceObject
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : Portcls.h
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
req.lib : portcls.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# ForwardContentToDeviceObject method
The <code>ForwardContentToDeviceObject</code> method accepts a device object representing a device to which the caller intends to forward protected content. Note that this method is identical in operation to the <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a> function, and its parameter definitions and return value are also identical.

## Syntax

````
NTSTATUS ForwardContentToDeviceObject();
````

## Parameters

`ContentId`



`Reserved`



`DrmForward`




## Return Value

See return value definition in <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>.

## Remarks

See comments in <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | portcls.h |

## See Also

<a href="..\portcls\nn-portcls-idrmport2.md">IDrmPort2</a>

<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IDrmPort2::ForwardContentToDeviceObject method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>