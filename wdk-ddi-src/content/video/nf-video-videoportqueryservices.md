---
UID: NF:video.VideoPortQueryServices
title: VideoPortQueryServices function
author: windows-driver-content
description: The VideoPortQueryServices function exposes a specified interface that is implemented by the video port driver.
old-location: display\videoportqueryservices.htm
old-project: display
ms.assetid: 88d54fbc-e865-4a59-bb1c-75adfb49c355
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortQueryServices, VideoPortQueryServices function [Display Devices], VideoPort_Functions_4f9cc677-4c65-4577-a289-92b8fb01c787.xml, display.videoportqueryservices, video/VideoPortQueryServices
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortQueryServices
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortQueryServices function
The <b>VideoPortQueryServices</b> function exposes a specified interface that is implemented by the video port driver.

## Syntax

```
VIDEOPORT_API VP_STATUS VideoPortQueryServices(
  IN PVOID               HwDeviceExtension,
  IN VIDEO_PORT_SERVICES ServicesType,
  IN OUT PINTERFACE      Interface
);
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`ServicesType`

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570540">VIDEO_PORT_SERVICES</a> enumerated type that specifies which interface is being requested.

`Interface`

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure, which contains basic information about the requested interface. See the following <b>Remarks</b> section for more information.


## Return Value

If <b>VideoPortQueryServices</b> succeeds, it returns NO_ERROR; otherwise, it returns an error code.

## Remarks

If the <i>ServicesType</i> parameter is set to <b>VideoPortServicesI2C</b>, the <i>Interface</i> parameter must be a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570538">VIDEO_PORT_I2C_INTERFACE</a> structure, cast as a pointer to an INTERFACE structure.

Similarly, if the <i>ServicesType</i> parameter is set to <b>VideoPortServicesAGP</b>, the <i>Interface</i> parameter must be a pointer to either a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570527">VIDEO_PORT_AGP_INTERFACE</a> structure, or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570528">VIDEO_PORT_AGP_INTERFACE_2</a> structure, each cast as a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure. 

The VIDEO_PORT_AGP_INTERFACE and VIDEO_PORT_AGP_INTERFACE_2 structures are nearly identical, except that the latter structure has a member that points to the <a href="https://msdn.microsoft.com/6885df05-8cc4-4ae0-b7ca-6fd94374cfbf">AgpSetRate</a> function, which is used to reset the transfer rate for an AGP chipset. A video miniport driver querying AGP support should call <b>VideoPortQueryServices</b> first with <i>Interface</i> pointing to a VIDEO_PORT_AGP_INTERFACE_2 structure. If that call fails, the miniport driver can then make another call to <b>VideoPortQueryServices</b>, this time with <i>Interface</i> pointing to a VIDEO_PORT_AGP_INTERFACE structure.

If the <i>ServicesType</i> parameter is set to <b>VideoPortServicesInt10</b>, the <i>Interface</i> parameter must be a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure, cast as a pointer to an INTERFACE structure.

If the <i>ServicesType</i> parameter is set to <b>VideoPortServicesDebugReport</b>, the <i>Interface</i> parameter must be a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570532">VIDEO_PORT_DEBUG_REPORT_INTERFACE</a> structure, cast as a pointer to an INTERFACE structure.

If the <i>ServicesType</i> parameter is set to <b>VideoPortServicesWCMemoryProtection</b>, the <i>Interface</i> parameter must be a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570541">VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE</a> structure, cast as a pointer to an INTERFACE structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/6885df05-8cc4-4ae0-b7ca-6fd94374cfbf">AgpSetRate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570527">VIDEO_PORT_AGP_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570528">VIDEO_PORT_AGP_INTERFACE_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570532">VIDEO_PORT_DEBUG_REPORT_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570538">VIDEO_PORT_I2C_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570541">VIDEO_PORT_WCMEMORYPROTECTION_INTERFACE</a>