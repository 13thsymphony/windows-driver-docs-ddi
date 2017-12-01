---
UID: NF.filterpipeline.IPrintWriteStreamFlush.FlushData
title: IPrintWriteStreamFlush::FlushData
author: windows-driver-content
description: The FlushData method flushes buffered data to a data stream while leaving the stream open, allowing the caller to write additional data to the stream.
old-location: print\iprintwritestreamflush_flushdata.htm
old-project: print
ms.assetid: F0E31AA1-47BD-4294-89BA-27B02FC8125B
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintWriteStreamFlush, FlushData, IPrintWriteStreamFlush::FlushData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintWriteStreamFlush.FlushData
req.alt-loc: filterpipeline.h
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
req.iface: IPrintWriteStreamFlush
---

# IPrintWriteStreamFlush::FlushData method



## -description
<p>The FlushData method flushes buffered data to a data stream while leaving the stream open, allowing the caller to write additional data to the stream.Writing to the stream is done using the <a href="print.iprintwritestream_writebytes">IPrintWriteStream::WriteBytes</a> method.</p>


## -syntax

````
HRESULT FlushData(
    None
);
````


## -parameters
<dl>

### -param <i>None</i> 

<dd>
<p>None</p>
</dd>
</dl>

## -returns
<p>The FlushData method returns an HRESULT value.</p>

## -remarks
<p>Only the last filter in the print filter pipeline benefits from the flush. The data is flushed to the port monitor. However, the port monitor has the option of using  buffers.</p>

<p>The following code snippet shows how to flush data to a data stream. Note that error checking has been omitted for clarity.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Filterpipeline.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.iprintwritestreamflush">IPrintWriteStreamFlush</a>
</dt>
<dt>
<a href="print.iprintwritestream_writebytes">IPrintWriteStream::WriteBytes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintWriteStreamFlush::FlushData method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
