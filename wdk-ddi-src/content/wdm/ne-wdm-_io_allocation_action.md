---
UID: NE:wdm._IO_ALLOCATION_ACTION
title: _IO_ALLOCATION_ACTION
author: windows-driver-content
description: The IO_ALLOCATION_ACTION enumerated type is used to specify return values for AdapterControl and ControllerControl routines.
old-location: kernel\io_allocation_action.htm
old-project: kernel
ms.assetid: 245d35a1-e877-4446-a0da-e50ece3656b1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _IO_ALLOCATION_ACTION, *PIO_ALLOCATION_ACTION, IO_ALLOCATION_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_ALLOCATION_ACTION
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
req.typenames: *PIO_ALLOCATION_ACTION, IO_ALLOCATION_ACTION
req.product: Windows 10 or later.
---

# _IO_ALLOCATION_ACTION enumeration



## -description
The <b>IO_ALLOCATION_ACTION</b> enumerated type is used to specify return values for <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff542049">ControllerControl</a> routines.



## -syntax

````
typedef enum _IO_ALLOCATION_ACTION { 
  KeepObject                     = 1,
  DeallocateObject               = 2,
  DeallocateObjectKeepRegisters  = 3
} IO_ALLOCATION_ACTION, *PIO_ALLOCATION_ACTION;
````


## -enum-fields

### -field KeepObject

Indicates that you want the driver to retain ownership of the adapter or controller object.


### -field DeallocateObject

Indicates that you do not want the driver to retain ownership of the adapter or controller object.


### -field DeallocateObjectKeepRegisters

<u>For adapter objects only.</u> Indicates that you do not want the driver to retain ownership of the adapter object, but you do want the driver to retain ownership of the allocated map registers. 


## -remarks
If an <i>AdapterControl</i> or <i>ControllerControl</i> routine completes an IRP, or if it can set up an operation (such as a disk seek) for a target device object that could be overlapped with an operation for another device object, it should return <b>DeallocateObject</b>.

If a driver uses packet-based bus-master DMA, its <i>AdapterControl</i> routine should return <b>DeallocateObjectKeepRegisters</b>.

Otherwise, the driver should return <b>KeepObject</b>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h or Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>