---
UID: NF.wdfhwaccess.WDF_READ_REGISTER_BUFFER_USHORT
title: WDF_READ_REGISTER_BUFFER_USHORT function
author: windows-driver-content
description: The WDF_READ_REGISTER_BUFFER_USHORT function reads a number of USHORT values from the specified register address into a buffer.
old-location: wdf\wdf_read_register_buffer_ushort.htm
old-project: wdf
ms.assetid: BA47B3D0-9515-40C6-B23D-A2D9FC993FB3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_READ_REGISTER_BUFFER_USHORT
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
req.alt-api: WDF_READ_REGISTER_BUFFER_USHORT
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

# WDF_READ_REGISTER_BUFFER_USHORT function



## -description
<p class="CCE_Message">[Applies to UMDF only]
The <b>WDF_READ_REGISTER_BUFFER_USHORT</b> function reads a number of USHORT values from the specified register address into a buffer.


## -syntax

````
void WDF_READ_REGISTER_BUFFER_USHORT(
  _In_  WDFDEVICE Device,
  _In_  PUSHORT   Register,
  _Out_ PUSHORT   Buffer,
  _In_  ULONG     Count 
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.

### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.

### -param Buffer [out]

A pointer to a buffer into which an array of USHORT values is read.

### -param Count  [in]

Specifies the number of USHORT values to be read into the buffer.

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