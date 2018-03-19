---
UID: NF:portcls.IDrmPort2.ForwardContentToDeviceObject
title: IDrmPort2::ForwardContentToDeviceObject method
author: windows-driver-content
description: The ForwardContentToDeviceObject method accepts a device object representing a device to which the caller intends to forward protected content.
old-location: audio\idrmport2_forwardcontenttodeviceobject.htm
old-project: audio
ms.assetid: 4e5c8942-3ce2-40d8-8cd7-436a5ebbc8ee
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ForwardContentToDeviceObject method [Audio Devices], ForwardContentToDeviceObject method [Audio Devices], IDrmPort2 interface, ForwardContentToDeviceObject,IDrmPort2.ForwardContentToDeviceObject, IDrmPort2, IDrmPort2 interface [Audio Devices], ForwardContentToDeviceObject method, IDrmPort2::ForwardContentToDeviceObject, audio.idrmport2_forwardcontenttodeviceobject, audmp-routines_6a59757e-e53e-4edb-aaa3-7dc695a1bc16.xml, portcls/IDrmPort2::ForwardContentToDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IDrmPort2.ForwardContentToDeviceObject
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
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

## See Also

<a href="..\portcls\nn-portcls-idrmport2.md">IDrmPort2</a>



<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>