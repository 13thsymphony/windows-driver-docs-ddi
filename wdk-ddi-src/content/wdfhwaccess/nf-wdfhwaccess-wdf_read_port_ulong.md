---
UID: NF:wdfhwaccess.WDF_READ_PORT_ULONG
title: WDF_READ_PORT_ULONG function
author: windows-driver-content
description: The WDF_READ_PORT_ULONG function reads a ULONG value from the specified port address.
old-location: wdf\wdf_read_port_ulong.htm
old-project: wdf
ms.assetid: 7553FE66-8138-4172-843F-84EE2D5A90BE
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WDF_READ_PORT_ULONG
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
req.alt-api: WDF_READ_PORT_ULONG
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

# WDF_READ_PORT_ULONG function



## -description
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_PORT_ULONG</b>  function reads a ULONG value from the specified port address.



## -syntax

````
ULONG WDF_READ_PORT_ULONG(
  _In_ WDFDEVICE Device,
  _In_ PULONG    Port
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space.


## -returns
<b>WDF_READ_PORT_ULONG</b> returns the ULONG value that is read from the specified port address.


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