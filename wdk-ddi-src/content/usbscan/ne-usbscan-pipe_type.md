---
UID: NE.usbscan.PIPE_TYPE
title: PIPE_TYPE
author: windows-driver-content
description: The PIPE_TYPE data type is used as input to the DeviceIoControl function, if the I/O control code is IOCTL_CANCEL_IO or IOCTL_RESET_PIPE.
old-location: image\pipe_type.htm
old-project: Image
ms.assetid: ae3077a3-01a8-4578-9a26-b8b14ec51a7a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PIPE_TYPE, PIPE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usbscan.h
req.include-header: Usbscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PIPE_TYPE
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
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# PIPE_TYPE enumeration



## -description
The <b>PIPE_TYPE</b> data type is used as input to the <a href="base.deviceiocontrol">DeviceIoControl</a> function, if the I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_cancel_io.md">IOCTL_CANCEL_IO</a> or <a href="..\usbscan\ni-usbscan-ioctl_reset_pipe.md">IOCTL_RESET_PIPE</a>. An interrupt pipe, a bulk IN pipe, and a bulk OUT pipe are associated with each device handle supplied to <b>DeviceIoControl</b>. The specified PIPE_TYPE value indicates on which of these pipes the operation should be performed, as indicated in the following table. 



## -syntax

````
typedef enum  { 
  EVENT_PIPE       = 0,
  READ_DATA_PIPE   = 1,
  WRITE_DATA_PIPE  = 2,
  ALL_PIPE         = 3
} PIPE_TYPE;
````


## -enum-fields

### -field EVENT_PIPE

The operation should be performed on the interrupt pipe.


### -field READ_DATA_PIPE

The operation should be performed on the bulk IN pipe.


### -field WRITE_DATA_PIPE

The operation should be performed on the bulk OUT pipe.


### -field ALL_PIPE

The operation should be performed on <i>all</i> transfer pipes (not just the pipes associated with the device handle supplied to <a href="base.deviceiocontrol">DeviceIoControl</a>).


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