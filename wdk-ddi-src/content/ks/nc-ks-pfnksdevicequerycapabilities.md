---
UID: NC:ks.PFNKSDEVICEQUERYCAPABILITIES
title: PFNKSDEVICEQUERYCAPABILITIES
author: windows-driver-content
description: An AVStream minidriver's AVStrMiniDeviceQueryCapabilities routine is called when an IRP_MN_QUERY_CAPABILITIES is dispatched by the device.
old-location: stream\avstrminidevicequerycapabilities.htm
old-project: stream
ms.assetid: 12084f07-5b6a-44d4-8ab3-325309e69372
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: AVStrMiniDeviceQueryCapabilities, AVStrMiniDeviceQueryCapabilities routine [Streaming Media Devices], PFNKSDEVICEQUERYCAPABILITIES, avstclbk_6078ead8-c11e-4f25-9742-21740e9a9da8.xml, ks/AVStrMiniDeviceQueryCapabilities, stream.avstrminidevicequerycapabilities
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ks.h
api_name:
-	AVStrMiniDeviceQueryCapabilities
product: Windows
targetos: Windows
req.typenames: SOUNDDETECTOR_PATTERNHEADER
---


# PFNKSDEVICEQUERYCAPABILITIES callback function
An AVStream minidriver's <i>AVStrMiniDeviceQueryCapabilities</i> routine is called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a> is dispatched by the device.

## Syntax

```
PFNKSDEVICEQUERYCAPABILITIES Pfnksdevicequerycapabilities;

NTSTATUS Pfnksdevicequerycapabilities(
  PKSDEVICE Device,
  PIRP Irp,
  PDEVICE_CAPABILITIES Capabilities
)
{...}
```

## Parameters

`Device`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a> that dispatched the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a>.

`Irp`

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a> issued by <i>Device</i>.

`Capabilities`

Pointer to the DEVICE_CAPABILITIES structure that describes PnP and Power capabilities of <i>Device</i>.


## Return Value

Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. Return success if providing query capabilities. If not, return an appropriate error code. Do not return STATUS_PENDING.

## Remarks

The minidriver specifies this routine's address in the <b>QueryCapabilities</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a> structure.

This routine is called when an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551664">IRP_MN_QUERY_CAPABILITIES</a> is dispatched by the device. It will usually be provided by minidrivers that need to supply information regarding power management capabilities. This routine is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | PASSIVE_LEVEL (See Remarks section) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561693">KSDEVICE_DISPATCH</a>