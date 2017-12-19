---
UID: NF.ndis.NdisFillMemory
title: NdisFillMemory macro
author: windows-driver-content
description: The NdisFillMemory function fills a caller-supplied buffer with the given character.
old-location: netvista\ndisfillmemory.htm
old-project: NetVista
ms.assetid: 6d974c56-5925-4ad5-a3c0-0c17e8488431
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisFillMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlFillMemory instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisFillMemory
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
---

# NdisFillMemory macro



## -description
The 
  <b>NdisFillMemory</b> function fills a caller-supplied buffer with the given character.



## -syntax

````
VOID NdisFillMemory(
  [in] PVOID Destination,
  [in] ULONG Length,
  [in] UCHAR Fill
);
````


## -parameters

### -param Destination [in]

A pointer to the buffer to be filled.


### -param Length [in]

The number of bytes to be filled.


### -param Fill [in]

The value to fill the buffer.


## -remarks
Callers of 
    <b>NdisFillMemory</b> can be running at any IRQL, provided that the 
    <i>Destination</i> buffer is resident. If the buffer is pageable, a caller must be running at IRQL &lt;
    DISPATCH_LEVEL.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use <a href="kernel.rtlfillmemory">RtlFillMemory</a> instead.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
See Remarks section

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.rtlequalmemory">RtlEqualMemory</a>
</dt>
<dt>
<a href="kernel.rtlzeromemory">RtlZeroMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisFillMemory macro%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

