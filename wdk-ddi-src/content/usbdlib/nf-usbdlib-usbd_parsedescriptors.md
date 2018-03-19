---
UID: NF:usbdlib.USBD_ParseDescriptors
title: USBD_ParseDescriptors function
author: windows-driver-content
description: The USBD_ParseDescriptors routine searches a given configuration descriptor and returns a pointer to the first descriptor that matches the search criteria.
old-location: buses\usbd_parsedescriptors.htm
old-project: usbref
ms.assetid: d6d90a4a-a67d-4ef3-82b8-7146970e30f3
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: USBD_ParseDescriptors, USBD_ParseDescriptors routine [Buses], buses.usbd_parsedescriptors, usbdlib/USBD_ParseDescriptors, usbfunc_a66c16e5-451c-4d5b-a621-4c4969200acd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbd.lib
-	Usbd.dll
api_name:
-	USBD_ParseDescriptors
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---


# USBD_ParseDescriptors function
The <b>USBD_ParseDescriptors</b> routine searches a given configuration descriptor and returns a pointer to the first descriptor that matches the search criteria.

## Syntax

````
PUSB_COMMON_DESCRIPTOR USBD_ParseDescriptors(
  _In_ PVOID DescriptorBuffer,
  _In_ ULONG TotalLength,
  _In_ PVOID StartPosition,
  _In_ LONG  DescriptorType
);
````

## Parameters

`DescriptorBuffer`

Pointer to a configuration descriptor that contains the descriptor for which to search.

`TotalLength`

Specifies the size, in bytes, of the buffer pointed to by <i>DescriptorBuffer</i>.

`StartPosition`

Pointer to the address within the configuration descriptor, provided at <i>DescriptorBuffer</i>, to begin searching from. To search from the beginning of the configuration descriptor, the parameters <i>DescriptorBuffer</i> and <i>StartPosition</i> must be the same address.

`DescriptorType`

Specifies the descriptor type code as assigned by USB. The following values are valid for USB-defined descriptor types:





#### USB_STRING_DESCRIPTOR_TYPE

Specifies that the descriptor being searched for is a string descriptor.



#### USB_INTERFACE_DESCRIPTOR_TYPE

Specifies that the descriptor being searched for is an interface descriptor.



#### USB_ENDPOINT_DESCRIPTOR_TYPE

Specifies that the descriptor being searched for is an endpoint descriptor.


## Return Value

<b>USBD_ParseDescriptors</b> returns a pointer to a <a href="..\usbspec\ns-usbspec-_usb_common_descriptor.md">USB_COMMON_DESCRIPTOR</a> structure that is the head of the first descriptor that matches the given search criteria, or <b>NULL</b> is returned if no match is found:

## Remarks

This structure is used to hold a portion of a descriptor, so that the caller of <b>USBD_ParseDescriptors</b> can determine the correct structure to use to access the remaining data in the descriptor. Every descriptor type has these fields at the beginning of the data and callers can use the <b>bLength</b> and <b>bDescriptorType</b> members to correctly identify the type of this descriptor.

When this routine parses the configuration descriptor looking for the descriptor that matches the search criteria, it returns the first match, terminating the search.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | usbdlib.h (include Usbdlib.h) |
| **Library** | Usbd.lib |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>