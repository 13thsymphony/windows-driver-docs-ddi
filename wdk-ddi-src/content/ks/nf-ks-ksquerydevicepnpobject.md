---
UID: NF:ks.KsQueryDevicePnpObject
title: KsQueryDevicePnpObject function
author: windows-driver-content
description: The KsQueryDevicePnpObject function returns the PnP device object that can be stored in the device header. This is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if KsDefaultDispatchPnp is used.
old-location: stream\ksquerydevicepnpobject.htm
old-project: stream
ms.assetid: 207b776a-8f51-4385-a171-a9d0e84e70b5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsQueryDevicePnpObject, KsQueryDevicePnpObject function [Streaming Media Devices], ks/KsQueryDevicePnpObject, ksfunc_dd821abc-bd3b-45e9-a1de-1f9fd201db8e.xml, stream.ksquerydevicepnpobject
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
-	KsQueryDevicePnpObject
product: Windows
targetos: Windows
req.typenames: 
---


# KsQueryDevicePnpObject function
The <b>KsQueryDevicePnpObject</b> function returns the PnP device object that can be stored in the device header. This is the next device object on the PnP stack and is the device object that PnP requests are forwarded to if <b>KsDefaultDispatchPnp</b> is used.

## Syntax

```
KSDDKAPI PDEVICE_OBJECT KsQueryDevicePnpObject(
  KSDEVICE_HEADER Header
);
```

## Parameters

`Header`

Points to a header previously allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff560958">KsAllocateDeviceHeader</a> whose PnP device object is to be returned.


## Return Value

The <b>KsQueryDevicePnpObject</b> function returns the previously set PnP device object. If none was set, it returns <b>NULL</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561665">KsDefaultDispatchPnp</a>