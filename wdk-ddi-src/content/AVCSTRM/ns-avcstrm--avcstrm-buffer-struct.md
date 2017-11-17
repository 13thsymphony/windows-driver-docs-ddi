---
UID: NS.avcstrm._AVCSTRM_BUFFER_STRUCT
title: AVCSTRM_BUFFER_STRUCT
author: windows-driver-content
description: The AVCSTRM_BUFFER_STRUCT structure describes a buffer to be submitted to avcstrm.sys for read or write operations.
old-location: stream\avcstrm_buffer_struct.htm
ms.assetid: ed9a5391-135d-4ac2-8b72-6a92d3ff9998
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: avcstrm.h
req.include-header: Avcstrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AVCSTRM_BUFFER_STRUCT
req.alt-loc: avcstrm.h
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
ms.keywords: AVCSTRM_BUFFER_STRUCT, AVCSTRM_BUFFER_STRUCT, *PAVCSTRM_BUFFER_STRUCT
req.iface: 
---

# AVCSTRM_BUFFER_STRUCT structure



## -description
<p>The AVCSTRM_BUFFER_STRUCT structure describes a buffer to be submitted to <i>avcstrm.sys</i> for read or write operations.</p>


## -syntax

````
typedef struct _AVCSTRM_BUFFER_STRUCT {
  BOOL             ClockProvider;
  HANDLE           ClockHandle;
  PKSSTREAM_HEADER StreamHeader;
  PVOID            FrameBuffer;
  PVOID            Context;
} AVCSTRM_BUFFER_STRUCT, *PAVCSTRM_BUFFER_STRUCT;
````


## -struct-fields
<dl>

### -field <b>ClockProvider</b>

<dd>
<p>Indicates whether the subunit driver itself serves as a clock provider. This is <b>TRUE</b> if this stream also serves as a clock provider, Otherwise, this is <b>FALSE</b>.</p>
</dd>

### -field <b>ClockHandle</b>

<dd>
<p>Specifies a handle to a clock provider other than the subunit driver itself.</p>
</dd>

### -field <b>StreamHeader</b>

<dd>
<p>Pointer to a kernel streaming header that describes a packet of data to be read from or written to a streaming driver pin.</p>
</dd>

### -field <b>FrameBuffer</b>

<dd>
<p>Pointer to a nonpaged system-space virtual address for the buffer described by the MDL.</p>
</dd>

### -field <b>Context</b>

<dd>
<p>Pointer to a client context value.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Avcstrm.h (include Avcstrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567138">KSSTREAM_HEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20AVCSTRM_BUFFER_STRUCT structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
