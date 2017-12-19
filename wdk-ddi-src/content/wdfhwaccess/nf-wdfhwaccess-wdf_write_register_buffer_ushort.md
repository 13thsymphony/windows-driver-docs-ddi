---
UID: NF.wdfhwaccess.WDF_WRITE_REGISTER_BUFFER_USHORT
title: WDF_WRITE_REGISTER_BUFFER_USHORT function
author: windows-driver-content
description: The WDF_WRITE_REGISTER_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified register.
old-location: wdf\wdf_write_register_buffer_ushort.htm
old-project: wdf
ms.assetid: EE076D50-8E08-4D98-872F-DA6DBA27B9E5
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WDF_WRITE_REGISTER_BUFFER_USHORT
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
req.alt-api: WDF_WRITE_REGISTER_BUFFER_USHORT
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
req.product: Windows 10 or later.
---

# WDF_WRITE_REGISTER_BUFFER_USHORT function



## -description
<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_WRITE_REGISTER_BUFFER_USHORT</b> routine writes a number of USHORT values from a buffer to the specified register.



## -syntax

````
void WDF_WRITE_REGISTER_BUFFER_USHORT(
  _In_ WDFDEVICE Device,
  _In_ PUSHORT   Register,
  _In_ PUSHORT   Buffer,
  _In_ ULONG     Count 
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Buffer [in]

A pointer to a buffer into which an array of USHORT values is to be written.


### -param Count  [in]

Specifies the number of USHORT values to write to the register.


## -returns
This function does not return a value.


## -remarks
The size of the buffer must be large enough to contain at least the specified number of bytes.


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