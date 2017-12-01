---
UID: NF.wdm.WRITE_PORT_USHORT
title: WRITE_PORT_USHORT
author: windows-driver-content
description: The WRITE_PORT_USHORT routine writes a USHORT value to the specified port address.
old-location: kernel\write_port_ushort.htm
old-project: kernel
ms.assetid: 60145cf3-62cb-4165-8536-f1546b9623dd
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WRITE_PORT_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WRITE_PORT_USHORT
req.alt-loc: Hal.lib,Hal.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: Any level (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# WRITE_PORT_USHORT function



## -description
<p>The <b>WRITE_PORT_USHORT</b> routine writes a USHORT value to the specified port address.</p>


## -syntax

````
 VOID WRITE_PORT_USHORT(
  _In_ PUSHORT Port,
  _In_ USHORT  Value
);
````


## -parameters
<dl>

### -param <i>Port</i> [in]

<dd>
<p>Pointer to the port, which must be a mapped memory range in I/O space.</p>
</dd>

### -param <i>Value</i> [in]

<dd>
<p>Specifies a USHORT value to be written to the port. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Callers of <b>WRITE_PORT_USHORT</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Hal.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level (see Remarks section)</p>
</td>
</tr>
</table>