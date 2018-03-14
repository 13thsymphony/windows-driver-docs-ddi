---
UID: NS:usbscan._IO_BLOCK
title: "_IO_BLOCK"
author: windows-driver-content
description: The IO_BLOCK structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_READ_REGISTERS or IOCTL_WRITE_REGISTERS.
old-location: image\io_block.htm
old-project: image
ms.assetid: aa1ccffc-c742-415d-8b72-fef247dff03c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PIO_BLOCK, IO_BLOCK, IO_BLOCK structure [Imaging Devices], PIO_BLOCK, PIO_BLOCK structure pointer [Imaging Devices], _IO_BLOCK, image.io_block, stifnc_94187a6f-5c01-4d4a-a852-469f93d891b9.xml, usbscan/IO_BLOCK, usbscan/PIO_BLOCK"
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
-	usbscan.h
api_name:
-	IO_BLOCK
product: Windows
targetos: Windows
req.typenames: IO_BLOCK, *PIO_BLOCK
req.product: Windows 10 or later.
---

# _IO_BLOCK structure
The IO_BLOCK structure is used as a parameter to <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>, when the specified I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_read_registers.md">IOCTL_READ_REGISTERS</a> or <a href="..\usbscan\ni-usbscan-ioctl_write_registers.md">IOCTL_WRITE_REGISTERS</a>. Values contained in structure members are used to create a USB Device Request (described in the <i>Universal Serial Bus Specification</i>).

## Syntax
````
typedef struct _IO_BLOCK {
  unsigned uOffset;
  unsigned uLength;
  PUCHAR   pbyData;
  unsigned uIndex;
} IO_BLOCK, *PIO_BLOCK;
````

## Members


`pbyData`

Pointer to a data buffer with a length of <b>uLength</b>.

`uIndex`

Used as the <b>Index</b> field of a USB Device Request.

`uLength`

Length of the buffer to transfer.

`uOffset`

Used as the <b>Value</b> field of a USB Device Request.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbscan.h (include Usbscan.h) |