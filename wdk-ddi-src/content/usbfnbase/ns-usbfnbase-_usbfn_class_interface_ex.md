---
UID: NS.USBFNBASE._USBFN_CLASS_INTERFACE_EX
title: _USBFN_CLASS_INTERFACE_EX
author: windows-driver-content
description: Describes an interface and its endpoints.
old-location: buses\usbfn_class_interface_ex.htm
old-project: usbref
ms.assetid: DEA417E7-FA4B-4F72-A03A-ECE921FC725C
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USBFN_CLASS_INTERFACE_EX, USBFN_CLASS_INTERFACE_EX, *PUSBFN_CLASS_INTERFACE_EX
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
req.alt-api: USBFN_CLASS_INTERFACE_EX
req.alt-loc: usbfnbase.h
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
req.product: Windows 10 or later.
---

# _USBFN_CLASS_INTERFACE_EX structure



## -description
Describes an interface and its endpoints.


## -syntax

````
typedef struct _USBFN_CLASS_INTERFACE_EX {
  UINT8                  BaseInterfaceNumber;
  UINT8                  InterfaceCount;
  UINT8                  PipeCount;
  USBFN_PIPE_INFORMATION PipeArr[MAX_NUM_USBFN_PIPES];
} USBFN_CLASS_INTERFACE_EX, *PUSBFN_CLASS_INTERFACE_EX;
````


## -struct-fields

### -field BaseInterfaceNumber

The index number of the interface.

### -field InterfaceCount

The number of USB interfaces contained in  the selected function.

### -field PipeCount

The number of endpoints contained in  the interface.

### -field PipeArr

An array of <a href="buses.usbfn_pipe_information">USBFN_PIPE_INFORMATION</a> structures that describes the endpoints in the interface.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Usbfnbase.h (include TBD)</dt>
</dl>
</td>
</tr>
</table>