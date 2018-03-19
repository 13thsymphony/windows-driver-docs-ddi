---
UID: NS:usbbusif._USBC_FUNCTION_DESCRIPTOR
title: "_USBC_FUNCTION_DESCRIPTOR"
author: windows-driver-content
description: The USBC_FUNCTION_DESCRIPTOR structure describes a USB function and its associated interface collection.
old-location: buses\usbc_function_descriptor.htm
old-project: usbref
ms.assetid: 43ac738b-7837-4183-ad06-5c35a2af38ff
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSBC_FUNCTION_DESCRIPTOR, PUSBC_FUNCTION_DESCRIPTOR, PUSBC_FUNCTION_DESCRIPTOR structure pointer [Buses], USBC_FUNCTION_DESCRIPTOR, USBC_FUNCTION_DESCRIPTOR structure [Buses], _USBC_FUNCTION_DESCRIPTOR, buses.usbc_function_descriptor, usbbusif/PUSBC_FUNCTION_DESCRIPTOR, usbbusif/USBC_FUNCTION_DESCRIPTOR, usbstrct_29623b3f-9def-4eb6-8735-eb695560ce27.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbbusif.h
api_name:
-	USBC_FUNCTION_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: USBC_FUNCTION_DESCRIPTOR, *PUSBC_FUNCTION_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USBC_FUNCTION_DESCRIPTOR structure
The <b>USBC_FUNCTION_DESCRIPTOR</b> structure describes a USB function and its associated interface collection.

## Syntax
````
typedef struct _USBC_FUNCTION_DESCRIPTOR {
  UCHAR                     FunctionNumber;
  UCHAR                     NumberOfInterfaces;
  PUSB_INTERFACE_DESCRIPTOR *InterfaceDescriptorList;
  UNICODE_STRING            HardwareId;
  UNICODE_STRING            CompatibleId;
  UNICODE_STRING            FunctionDescription;
  ULONG                     FunctionFlags;
  PVOID                     Reserved;
} USBC_FUNCTION_DESCRIPTOR, *PUSBC_FUNCTION_DESCRIPTOR;
````

## Members


`FunctionNumber`

The zero-based index of the interface collection.

`NumberOfInterfaces`

The number of interfaces in the interface collection.

`InterfaceDescriptorList`

An array of pointers to <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>-type structures that describe the interfaces in the interface collection.

`HardwareId`

The hardware identifier of the interface collection.

`CompatibleId`

The compatible identifier of the interface collection.

`FunctionDescription`

A description of the interface collection in human-readable text.

`FunctionFlags`

Vendor-defined flags that describe the interface collection.

`Reserved`

Reserved.

## Remarks
For information on how to use user-defined callback routines to provide a custom definition of the interface collections on a device, see <a href="https://msdn.microsoft.com/3cf4e9f2-ea33-491f-94af-62d2afacc899">Customizing Enumeration of Interface Collections for Composite Devices</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbbusif.h (include Usbbusif.h) |

## See Also

<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>