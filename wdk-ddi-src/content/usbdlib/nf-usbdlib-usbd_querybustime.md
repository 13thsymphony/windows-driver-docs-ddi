---
UID: NF:usbdlib.USBD_QueryBusTime
title: USBD_QueryBusTime function
author: windows-driver-content
description: The USBD_QueryBusTime routine has been deprecated in Windows XP and later operating systems. Do not use.
old-location: buses\usbd_querybustime.htm
old-project: usbref
ms.assetid: ae59daf6-da7b-4b04-bb5c-dfd353b937a0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: USBD_QueryBusTime, USBD_QueryBusTime routine [Buses], buses.usbd_querybustime, usbdlib/USBD_QueryBusTime, usbfunc_2911ce15-3106-4c66-95c8-52ff57318131.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Deprecated.
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
req.lib: Usbd.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbd.lib
-	Usbd.dll
api_name:
-	USBD_QueryBusTime
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---


# USBD_QueryBusTime function
The <b>USBD_QueryBusTime</b> routine has been deprecated in Windows XP and later operating systems. Do not use. 

See URB_FUNCTION_GET_CURRENT_FRAME_NUMBER for equivalent functionality that is supported on all versions of Windows.

## Syntax

````
void USBD_QueryBusTime(
  _In_  PDEVICE_OBJECT RootHubPdo,
  _Out_ PULONG         CurrentFrame
);
````

## Parameters

`RootHubPdo`

Obsolete.

`CurrentFrame`

Obsolete.


## Return Value

This routine does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Deprecated.  |
| **Target Platform** | Universal |
| **Header** | usbdlib.h |
| **Library** | Usbd.lib |

## See Also

<a href="..\usb\ns-usb-_urb_get_current_frame_number.md">URB_GET_CURRENT_FRAME_NUMBER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>