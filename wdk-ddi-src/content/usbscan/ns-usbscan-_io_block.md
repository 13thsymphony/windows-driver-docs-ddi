---
UID: NS:usbscan._IO_BLOCK
title: _IO_BLOCK
author: windows-driver-content
description: The IO_BLOCK structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_READ_REGISTERS or IOCTL_WRITE_REGISTERS.
old-location: image\io_block.htm
old-project: image
ms.assetid: aa1ccffc-c742-415d-8b72-fef247dff03c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _IO_BLOCK, *PIO_BLOCK, IO_BLOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IO_BLOCK
req.alt-loc: usbscan.h
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
req.typenames: *PIO_BLOCK, IO_BLOCK
req.product: Windows 10 or later.
---

# _IO_BLOCK structure



## -description
The IO_BLOCK structure is used as a parameter to <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>, when the specified I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_read_registers.md">IOCTL_READ_REGISTERS</a> or <a href="..\usbscan\ni-usbscan-ioctl_write_registers.md">IOCTL_WRITE_REGISTERS</a>. Values contained in structure members are used to create a USB Device Request (described in the <i>Universal Serial Bus Specification</i>).



## -syntax

````
typedef struct _IO_BLOCK {
  unsigned uOffset;
  unsigned uLength;
  PUCHAR   pbyData;
  unsigned uIndex;
} IO_BLOCK, *PIO_BLOCK;
````


## -struct-fields

### -field uOffset

Used as the <b>Value</b> field of a USB Device Request.


### -field uLength

Length of the buffer to transfer.


### -field pbyData

Pointer to a data buffer with a length of <b>uLength</b>.


### -field uIndex

Used as the <b>Index</b> field of a USB Device Request.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbscan.h (include Usbscan.h)</dt>
</dl>
</td>
</tr>
</table>