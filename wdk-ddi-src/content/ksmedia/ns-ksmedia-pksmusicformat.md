---
UID: NS.ksmedia.PKSMUSICFORMAT
title: PKSMUSICFORMAT
author: windows-driver-content
description: The KSMUSICFORMAT structure is used to send and receive information about MIDI data that is input from and output to WDM audio devices.
old-location: audio\ksmusicformat.htm
old-project: audio
ms.assetid: 836e2eb5-b8cf-4c12-a855-f63709622c74
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSMUSICFORMAT, KSMUSICFORMAT, *PKSMUSICFORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSMUSICFORMAT
req.alt-loc: ksmedia.h
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
req.iface: 
---

# PKSMUSICFORMAT structure



## -description
<p>The KSMUSICFORMAT structure is used to send and receive information about MIDI data that is input from and output to WDM audio devices.</p>


## -syntax

````
typedef struct {
  ULONG TimeDeltaMs;
  ULONG ByteCount;
} KSMUSICFORMAT, *PKSMUSICFORMAT;
````


## -struct-fields
<dl>

### -field <b>TimeDeltaMs</b>

<dd>
<p>Indicates when this series of MIDI data bytes should be played. If this is the first KSMUSICFORMAT structure in the buffer, this field represents the delta (time change, in milliseconds) from the <b>PresentationTime</b> in the <a href="stream.ksstream_header">KSSTREAM_HEADER</a> structure. Otherwise, the field represents the delta offset (in milliseconds) from the previous message (KSMUSICFORMAT structure). If this time is in the past, then the message is played immediately.</p>
</dd>

### -field <b>ByteCount</b>

<dd>
<p>Specifies the number of bytes of data that follow this structure. Because the subsequent structure or properties should be DWORD aligned and might allow for extra blanks or used bytes, <b>ByteCount</b> should be the actual number of bytes present and not include any padding separating the data structures.</p>
</dd>
</dl>

## -remarks
<p>This structure is used to send and receive IRPs containing information about MIDI input and output streams. The IRP itself contains in its <b>SystemBuffer</b> field a pointer to a KSSTREAM_HEADER structure, which serves as a header for a packet of data that is to be read from or written to a streaming driver pin. The KS stream header contains in its <b>Data</b> field a pointer to the buffer that contains the data. The data in that buffer consists of a sequence of messages, each of which is a KSMUSICFORMAT structure that is immediately followed by some number of bytes of data.</p>

<p>Time stamps in these IRPs always increase across successively issued IRPs. However, because each IRP in a sequence is fully serviced before servicing of the next IRP begins, time must also always increase across IRPs. This can lead to an anomalous situation, as described in the following example.</p>

<p>IRP #1 PresentationTime = 123 milliseconds</p>

<p>Message #1 TimeDeltaMs: 0</p>

<p>Will be played at 123 milliseconds.</p>

<p>Message #2 TimeDeltaMs: 1</p>

<p>Will be played at 124 milliseconds.</p>

<p>Message #3 TimeDeltaMs: 7</p>

<p>Will be played at 131 milliseconds.</p>

<p>IRP #2 PresentationTime = 120 milliseconds</p>

<p>Message #1 TimeDeltaMs: 5</p>

<p>Supposed to be played at 125 milliseconds, but is actually played at 131 milliseconds. This IRP is not processed until the previous IRP at 131 milliseconds finishes.</p>

<p>Message #2 TimeDeltaMs: 15</p>

<p>Will be played at 140 milliseconds.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksstream_header">KSSTREAM_HEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSMUSICFORMAT structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
