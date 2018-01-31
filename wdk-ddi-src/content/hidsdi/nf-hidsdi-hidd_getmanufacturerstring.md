---
UID : NF:hidsdi.HidD_GetManufacturerString
title : HidD_GetManufacturerString function
author : windows-driver-content
description : The HidD_GetManufacturerString routine returns a top-level collection's embedded string that identifies the manufacturer.
old-location : hid\hidd_getmanufacturerstring.htm
old-project : hid
ms.assetid : 21253ed7-d98d-4b97-8d83-01dd18b3c4f9
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : hidsdi/HidD_GetManufacturerString, HidD_GetManufacturerString, hid.hidd_getmanufacturerstring, hidfunc_c0e9df6e-0aab-49ac-9a72-196a9b3ceec5.xml, HidD_GetManufacturerString routine [Human Input Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : hidsdi.h
req.include-header : Hidsdi.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 2000 and later versions of Windows.
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
req.lib : Hid.lib
req.dll : Hid.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PHID_MINIDRIVER_REGISTRATION, HID_MINIDRIVER_REGISTRATION"
---


# HidD_GetManufacturerString function
The <b>HidD_GetManufacturerString</b> routine returns a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> embedded string that identifies the manufacturer.

## Syntax

````
BOOLEAN __stdcall HidD_GetManufacturerString(
  _In_  HANDLE HidDeviceObject,
  _Out_ PVOID  Buffer,
  _In_  ULONG  BufferLength
);
````

## Parameters

`HidDeviceObject`

Specifies an open handle to a top-level collection.

`Buffer`

Pointer to a caller-allocated buffer that the routine uses to return the collection's manufacturer string. The routine returns a NULL-terminated wide character string in a human-readable format.

`BufferLength`

Specifies the length, in bytes, of a caller-allocated buffer provided at <i>Buffer</i>. If the buffer is not large enough to return the entire NULL-terminated embedded string, the routine returns nothing in the buffer.


## Return Value

HidD_HidD_GetManufacturerString returns <b>TRUE</b> if it returns the entire NULL-terminated embedded string. Otherwise, the routine returns <b>FALSE</b>.

## Remarks

Only user-mode applications can call <b>HidD_GetManufacturerString</b>. Kernel-mode drivers can use an <a href="..\hidclass\ni-hidclass-ioctl_hid_get_manufacturer_string.md">IOCTL_HID_GET_MANUFACTURER_STRING</a> request.

The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

For more information, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hidsdi.h (include Hidsdi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_indexed_string.md">IOCTL_HID_GET_INDEXED_STRING</a>

<a href="..\hidsdi\nf-hidsdi-hidd_getproductstring.md">HidD_GetProductString</a>

<a href="..\hidsdi\nf-hidsdi-hidd_getserialnumberstring.md">HidD_GetSerialNumberString</a>

<a href="..\hidsdi\nf-hidsdi-hidd_getphysicaldescriptor.md">HidD_GetPhysicalDescriptor</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_manufacturer_string.md">IOCTL_HID_GET_MANUFACTURER_STRING</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_serialnumber_string.md">IOCTL_HID_GET_SERIALNUMBER_STRING</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_product_string.md">IOCTL_HID_GET_PRODUCT_STRING</a>

<a href="..\hidsdi\nf-hidsdi-hidd_getindexedstring.md">HidD_GetIndexedString</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HidD_GetManufacturerString routine%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>