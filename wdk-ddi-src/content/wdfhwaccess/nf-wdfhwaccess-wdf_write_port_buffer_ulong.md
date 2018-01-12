---
UID: NF:wdfhwaccess.WDF_WRITE_PORT_BUFFER_ULONG
title: WDF_WRITE_PORT_BUFFER_ULONG function
author: windows-driver-content
description: The WDF_WRITE_PORT_BUFFER_ULONG function writes a number of ULONG values from a buffer to the specified port address.
old-location: wdf\wdf_write_port_buffer_ulong.htm
old-project: wdf
ms.assetid: 4FBBC349-B6D0-4F99-AF34-FA237199431E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WDF_WRITE_PORT_BUFFER_ULONG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfhwaccess.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.alt-api: WDF_WRITE_PORT_BUFFER_ULONG
req.alt-loc: Wdfhwaccess.h
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
req.typenames: *PWDF_FILE_INFORMATION_CLASS, WDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WDF_WRITE_PORT_BUFFER_ULONG function



## -description
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_WRITE_PORT_BUFFER_ULONG</b> function writes a number of ULONG values from a buffer to the specified port address.




## -syntax

````
void WDF_WRITE_PORT_BUFFER_ULONG(
  _In_ WDFDEVICE Device,
  _In_ PULONG    Port,
  _In_ PULONG    Buffer,
  _In_ ULONG     Count 
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Port [in]

A pointer to the port, which must be a mapped memory range in I/O space.


### -param Buffer [in]

A pointer to a buffer from which an array of ULONG values is to be written.



### -param Count  [in]

Specifies the number of ULONG values to be written to the buffer.


## -returns
This function does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum support

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfhwaccess.h</dt>
</dl>
</td>
</tr>
</table>