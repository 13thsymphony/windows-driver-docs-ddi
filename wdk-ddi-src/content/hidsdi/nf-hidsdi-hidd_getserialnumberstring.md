---
UID: NF:hidsdi.HidD_GetSerialNumberString
title: HidD_GetSerialNumberString function
author: windows-driver-content
description: The HidD_GetSerialNumberString routine returns the embedded string of a top-level collection that identifies the serial number of the collection's physical device.
old-location: hid\hidd_getserialnumberstring.htm
old-project: hid
ms.assetid: 807f1432-1b2f-45fc-899c-b2920ea79f7a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: HidD_GetSerialNumberString, HidD_GetSerialNumberString routine [Human Input Devices], hid.hidd_getserialnumberstring, hidfunc_b01ce302-052c-43f1-9b8f-6421ebb66954.xml, hidsdi/HidD_GetSerialNumberString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hid.dll
api_name:
-	HidD_GetSerialNumberString
product: Windows
targetos: Windows
req.typenames: HID_MINIDRIVER_REGISTRATION, *PHID_MINIDRIVER_REGISTRATION
---


# HidD_GetSerialNumberString function
The <b>HidD_GetSerialNumberString</b> routine returns the embedded string of a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a> that identifies the serial number of the collection's physical device.

## Syntax

```
BOOLEAN HidD_GetSerialNumberString(
  HANDLE HidDeviceObject,
  PVOID  Buffer,
  ULONG  BufferLength
);
```

## Parameters

`HidDeviceObject`

Specifies an open handle to a top-level collection.

`Buffer`

Pointer to a caller-allocated buffer that the routine uses to return the requested serial number string. The routine returns a NULL-terminated wide character string.

`BufferLength`

Specifies the length, in bytes, of a caller-allocated buffer provided at <i>Buffer</i>. If the buffer is not large enough to return the entire NULL-terminated embedded string, the routine returns nothing in the buffer.


## Return Value

<b>HidD_GetSerialNumberString</b> returns <b>TRUE</b> if it successfully returns the entire NULL-terminated embedded string. Otherwise, the routine returns <b>FALSE</b>.

## Remarks

Only user-mode applications can call <b>HidD_GetSerialNumberString</b>. Kernel-mode drivers can use <a href="https://msdn.microsoft.com/library/windows/hardware/ff541160">IOCTL_HID_GET_SERIALNUMBER_STRING</a>.

The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | hidsdi.h (include Hidsdi.h) |
| **Library** | Hid.lib |
| **DLL** | Hid.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538959">HidD_GetManufacturerString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539677">HidD_GetPhysicalDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539681">HidD_GetProductString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541109">IOCTL_HID_GET_INDEXED_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541134">IOCTL_HID_GET_MANUFACTURER_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541146">IOCTL_HID_GET_PRODUCT_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541160">IOCTL_HID_GET_SERIALNUMBER_STRING</a>