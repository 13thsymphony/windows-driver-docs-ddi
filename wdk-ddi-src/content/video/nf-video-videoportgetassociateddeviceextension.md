---
UID: NF:video.VideoPortGetAssociatedDeviceExtension
title: VideoPortGetAssociatedDeviceExtension function
author: windows-driver-content
description: The VideoPortGetAssociatedDeviceExtension function returns the device extension for the parent of the specified device object.
old-location: display\videoportgetassociateddeviceextension.htm
old-project: display
ms.assetid: 825e2b61-6b51-4553-88e1-0aff2e9e3cce
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPort_Functions_7116b537-1296-4136-b62c-ce5918eea10d.xml, display.videoportgetassociateddeviceextension, video/VideoPortGetAssociatedDeviceExtension, VideoPortGetAssociatedDeviceExtension, VideoPortGetAssociatedDeviceExtension function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortGetAssociatedDeviceExtension
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortGetAssociatedDeviceExtension function
The <b>VideoPortGetAssociatedDeviceExtension</b> function returns the device extension for the parent of the specified device object.

## Syntax

````
PVOID VideoPortGetAssociatedDeviceExtension(
  _In_ PVOID DeviceObject
);
````

## Parameters

`DeviceObject`

Is the device object of a child device.


## Return Value

<b>VideoPortGetAssociatedDeviceExtension</b> returns a pointer to the device extension of <i>DeviceObject</i>'s parent.

## Remarks

The miniport driver of a child device can call this function to obtain a description of its parent through the parent's device extension.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems. Available in Windows 2000 and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | PASSIVE_LEVEL |