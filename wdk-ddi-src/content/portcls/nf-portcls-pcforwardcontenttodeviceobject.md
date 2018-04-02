---
UID: NF:portcls.PcForwardContentToDeviceObject
title: PcForwardContentToDeviceObject function
author: windows-driver-content
description: The PcForwardContentToDeviceObject function accepts a device object representing a device to which the caller intends to forward protected content.
old-location: audio\pcforwardcontenttodeviceobject.htm
old-project: audio
ms.assetid: 24891f90-422f-4104-97f4-395205e2b862
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: PcForwardContentToDeviceObject, PcForwardContentToDeviceObject function [Audio Devices], audio.pcforwardcontenttodeviceobject, audpc-routines_1dec7e58-07b2-41ce-82d3-5f0670bbc273.xml, portcls/PcForwardContentToDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcForwardContentToDeviceObject function in Microsoft Windows XP and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcForwardContentToDeviceObject
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcForwardContentToDeviceObject function
The <b>PcForwardContentToDeviceObject</b> function accepts a device object representing a device to which the caller intends to forward protected content. Note that this function call is identical in operation to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a> function, and its parameter definitions and return value are also identical.

## Syntax

```
PORTCLASSAPI NTSTATUS PcForwardContentToDeviceObject(
  ULONG        ContentId,
  PVOID        Reserved,
  PCDRMFORWARD DrmForward
);
```

## Parameters

`ContentId`

Specifies the DRM content ID. This parameter identifies a protected KS audio stream.

`Reserved`

Reserved for future use. Set to <b>NULL</b>.

`DrmForward`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff536350">DRMFORWARD</a> structure specifying a device object and file object that identify the target device and a KS audio pin on that device, respectively. The structure also contains the context value that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request passes to the device.


## Return Value

See return value definition in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>.

## Remarks

For more information, see the comments in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The PortCls system driver implements the PcForwardContentToDeviceObject function in Microsoft Windows XP and later operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536351">DrmForwardContentToDeviceObject</a>