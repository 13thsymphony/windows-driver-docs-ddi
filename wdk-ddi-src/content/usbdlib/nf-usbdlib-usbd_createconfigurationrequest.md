---
UID: NF:usbdlib.USBD_CreateConfigurationRequest
title: USBD_CreateConfigurationRequest function
author: windows-driver-content
description: The USBD_CreateConfigurationRequest routine has been deprecated. Use USBD_CreateConfigurationRequestEx instead.
old-location: buses\usbd_createconfigurationrequest.htm
old-project: usbref
ms.assetid: e1f397f6-2f33-4352-9bbc-2b2a49dcd067
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: USBD_CreateConfigurationRequest, USBD_CreateConfigurationRequest routine [Buses], buses.usbd_createconfigurationrequest, usbdlib/USBD_CreateConfigurationRequest, usbfunc_d2701cb6-8159-48e0-b668-bb3b02226a7d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Deprecated. Use USBD_CreateConfigurationRequestEx instead.
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
-	USBD_CreateConfigurationRequest
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---


# USBD_CreateConfigurationRequest function
The  <b>USBD_CreateConfigurationRequest</b> routine has been deprecated. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff539029">USBD_CreateConfigurationRequestEx</a> instead.

## Syntax

```
DECLSPEC_IMPORT PURB USBD_CreateConfigurationRequest(
  PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
  PUSHORT                       Siz
);
```

## Parameters

`ConfigurationDescriptor`

Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a> structure that contains the configuration descriptor for the configuration to be selected.

`Siz`

Size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure.


## Return Value

<b>USBD_CreateConfigurationRequest</b> allocates a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure, formats it for the URB_FUNCTION_SELECT_CONFIGURATION request (select-configuration request), and returns a pointer to the <b>URB</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Deprecated. Use USBD_CreateConfigurationRequestEx instead.  |
| **Target Platform** | Universal |
| **Header** | usbdlib.h |
| **Library** | Usbd.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539029">USBD_CreateConfigurationRequestEx</a>