---
UID: NF:usbdlib.USBD_ValidateConfigurationDescriptor
title: USBD_ValidateConfigurationDescriptor function
author: windows-driver-content
description: The USBD_ValidateConfigurationDescriptor routine validates all descriptors returned by a device in its response to a configuration descriptor request.
old-location: buses\usbd_validateconfigurationdescriptor.htm
old-project: usbref
ms.assetid: 2fbe08ca-a9eb-4e3b-aa28-1ff34ad22a46
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: USBD_ValidateConfigurationDescriptor, USBD_ValidateConfigurationDescriptor routine [Buses], buses.usbd_validateconfigurationdescriptor, usbdlib/USBD_ValidateConfigurationDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbd.lib
-	Usbd.dll
api_name:
-	USBD_ValidateConfigurationDescriptor
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---


# USBD_ValidateConfigurationDescriptor function
The <b>USBD_ValidateConfigurationDescriptor</b> routine validates all descriptors returned by a device in its response to a configuration descriptor request.

## Syntax

```
DECLSPEC_IMPORT USBD_STATUS USBD_ValidateConfigurationDescriptor(
  PUSB_CONFIGURATION_DESCRIPTOR ConfigDesc,
  ULONG                         BufferLength,
  USHORT                        Level,
  PUCHAR                        *Offset,
  ULONG                         Tag
);
```

## Parameters

`ConfigDesc`

Pointer to a configuration descriptor that includes all interface, endpoint, vendor, and class-specific descriptors retrieved from a USB device.

`BufferLength`

Size, in bytes, of the configuration descriptor being validated.

`Level`

Level of validation to be performed.  The following are valid values:

<ul>
<li>1-Basic validation of the configuration descriptor header.</li>
<li>2-Full validation of the configuration descriptor including checking for invalid endpoint addresses, interface numbers, descriptor structures, interface alternate settings, number of interfaces and <b>bLength</b> fields of all descriptors.               
</li>
<li>3-In addition to the validation for levels 1 and 2, level 3 validates plus validates the number of endpoints in each interface, enforces the USB specification's descriptor <b>bLength</b> sizes, and verifies that all interface numbers are in sequential order.</li>
</ul>

`Offset`

Offset within configuration descriptor where validation failed.  Only valid when a status other than USBD_STATUS_SUCCESS is returned.

`Tag`

Pool tag used by <b>USBD_ValidateConfigurationDescriptor</b> when allocating memory.


## Return Value

USBD_STATUS_SUCCESS, or appropriate USBD error code if validation failed.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating systems.  |
| **Target Platform** | Universal |
| **Header** | usbdlib.h (include Usbdlib.h) |
| **Library** | Usbd.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>