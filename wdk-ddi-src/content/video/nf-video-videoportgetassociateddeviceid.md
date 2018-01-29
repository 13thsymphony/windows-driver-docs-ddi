---
UID : NF:video.VideoPortGetAssociatedDeviceID
title : VideoPortGetAssociatedDeviceID function
author : windows-driver-content
description : The VideoPortGetAssociatedDeviceID function obtains the child ID for a specified device object.
old-location : display\videoportgetassociateddeviceid.htm
old-project : display
ms.assetid : 6c40f98b-4d93-4ee8-8217-51e6f1170cf8
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : VideoPortGetAssociatedDeviceID, VideoPortGetAssociatedDeviceID function [Display Devices], display.videoportgetassociateddeviceid, VideoPort_Functions_56a3fa57-fd1a-4b45-8de7-ee9450a525f4.xml, video/VideoPortGetAssociatedDeviceID
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : video.h
req.include-header : Video.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows XP and later versions of the Windows operating systems.
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
req.lib : Videoprt.lib
req.dll : Videoprt.sys
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VIDEO_PORT_SERVICES
req.product : Windows 10 or later.
---


# VideoPortGetAssociatedDeviceID function
The <b>VideoPortGetAssociatedDeviceID</b> function obtains the child ID for a specified device object.

## Syntax

````
ULONG VideoPortGetAssociatedDeviceID(
  _In_ PVOID DeviceObject
);
````

## Parameters

`DeviceObject`

Pointer to the child device object, a <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDO</a>.


## Return Value

<b>VideoPortGetAssociatedDeviceID</b> returns the child ID for the given device object.

## Remarks

<b>VideoPortGetAssociatedDeviceID</b> can be used to obtain the child ID for a child device object. For example, this is useful with <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">I2C</a>. See <a href="https://msdn.microsoft.com/5eea2257-49ca-4d76-a6a1-91401595750f">Using I2C to Communicate with a Child Device</a> for more information.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |