---
UID: NS:usbfnbase._USBFN_CLASS_INTERFACE_EX
title: "_USBFN_CLASS_INTERFACE_EX"
author: windows-driver-content
description: Describes an interface and its endpoints.
old-location: buses\usbfn_class_interface_ex.htm
old-project: usbref
ms.assetid: DEA417E7-FA4B-4F72-A03A-ECE921FC725C
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSBFN_CLASS_INTERFACE_EX, PUSBFN_CLASS_INTERFACE_EX, PUSBFN_CLASS_INTERFACE_EX structure pointer [Buses], USBFN_CLASS_INTERFACE_EX, USBFN_CLASS_INTERFACE_EX structure [Buses], _USBFN_CLASS_INTERFACE_EX, buses.usbfn_class_interface_ex, usbfnbase/PUSBFN_CLASS_INTERFACE_EX, usbfnbase/USBFN_CLASS_INTERFACE_EX"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbfnbase.h
req.include-header: TBD
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnbase.h
api_name:
-	USBFN_CLASS_INTERFACE_EX
product: Windows
targetos: Windows
req.typenames: USBFN_CLASS_INTERFACE_EX, *PUSBFN_CLASS_INTERFACE_EX
req.product: Windows 10 or later.
---

# _USBFN_CLASS_INTERFACE_EX structure
Describes an interface and its endpoints.

## Syntax
````
typedef struct _USBFN_CLASS_INTERFACE_EX {
  UINT8                  BaseInterfaceNumber;
  UINT8                  InterfaceCount;
  UINT8                  PipeCount;
  USBFN_PIPE_INFORMATION PipeArr[MAX_NUM_USBFN_PIPES];
} USBFN_CLASS_INTERFACE_EX, *PUSBFN_CLASS_INTERFACE_EX;
````

## Members


`BaseInterfaceNumber`

The index number of the interface.

`InterfaceCount`

The number of USB interfaces contained in  the selected function.

`PipeCount`

The number of endpoints contained in  the interface.

`PipeArr`

An array of <a href="..\usbfnbase\ns-usbfnbase-_usbfn_pipe_information.md">USBFN_PIPE_INFORMATION</a> structures that describes the endpoints in the interface.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbfnbase.h (include TBD) |