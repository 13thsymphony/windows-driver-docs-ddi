---
UID: NF:portcls.PcGetPhysicalDeviceObject
title: PcGetPhysicalDeviceObject function
author: windows-driver-content
description: The PcGetPhysicalDeviceObject function enables audio miniport drivers to retrieve the underlying physical device object of the audio device.
old-location: audio\pcgetphysicaldeviceobject.htm
old-project: audio
ms.assetid: A7917082-4C3F-445A-AD26-32DE670754E5
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PcGetPhysicalDeviceObject, PcGetPhysicalDeviceObject function [Audio Devices], audio.pcgetphysicaldeviceobject, portcls/PcGetPhysicalDeviceObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting in Windows 8.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcGetPhysicalDeviceObject
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcGetPhysicalDeviceObject function
The <b>PcGetPhysicalDeviceObject</b> function enables audio miniport drivers to retrieve the  underlying physical device object of the audio device.

## Syntax

````
PORTCLASSAPI NTSTATUS NTAPI PcGetPhysicalDeviceObject(
  _In_  PDEVICE_OBJECT pDeviceObject,
  _Out_ PDEVICE_OBJECT ppPhysicalObject
);
````

## Parameters

`pDeviceObject`

Pointer to the device object for the device.

`ppPhysicalObject`

Pointer to the physical object for the device.


## Return Value

The <b>PcGetPhysicalDeviceObject</b> function returns STATUS_SUCCESS if the function call was successful. Otherwise, it returns the appropriate error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting in Windows 8.  |
| **Target Platform** | Universal |
| **Header** | portcls.h |
| **Library** | Portcls.lib |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536208">Audio Port Class Functions</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcGetPhysicalDeviceObject function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>