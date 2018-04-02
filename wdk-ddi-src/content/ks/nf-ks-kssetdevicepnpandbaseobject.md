---
UID: NF:ks.KsSetDevicePnpAndBaseObject
title: KsSetDevicePnpAndBaseObject function
author: windows-driver-content
description: The KsSetDevicePnpAndBaseObject function sets the PnP device object in the device header, which is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if KsDefaultDispatchPnp is used.
old-location: stream\kssetdevicepnpandbaseobject.htm
old-project: stream
ms.assetid: 269bbb79-c730-4b78-bf46-d502f23f039b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsSetDevicePnpAndBaseObject, KsSetDevicePnpAndBaseObject function [Streaming Media Devices], ks/KsSetDevicePnpAndBaseObject, ksfunc_eff06a34-a458-4426-972c-6a0fbf0f7846.xml, stream.kssetdevicepnpandbaseobject
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsSetDevicePnpAndBaseObject
product: Windows
targetos: Windows
req.typenames: 
---


# KsSetDevicePnpAndBaseObject function
The <b>KsSetDevicePnpAndBaseObject</b> function sets the PnP device object in the device header, which is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if <b>KsDefaultDispatchPnp</b> is used.

## Syntax

```
KSDDKAPI VOID KsSetDevicePnpAndBaseObject(
  KSDEVICE_HEADER Header,
  PDEVICE_OBJECT  PnpDeviceObject,
  PDEVICE_OBJECT  BaseObject
);
```

## Parameters

`Header`

Points to a header previously allocated by <b>KsAllocateDeviceHeader</b> in which to put the PnP device object.

`PnpDeviceObject`

Specifies the PnP device object to place in the device header, overwriting any previously set device object.

`BaseObject`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560958">KsAllocateDeviceHeader</a>



<a href="https://msdn.microsoft.com/0b8f23a5-af8a-4b99-8f17-092076523914">KsRecalculateStackDepth</a>