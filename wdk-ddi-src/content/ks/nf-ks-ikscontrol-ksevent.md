---
UID: NF.ks.IKsControl.KsEvent
title: IKsControl::KsEvent
author: windows-driver-content
description: The IKsControl::KsEvent method enables or disables an event, together with any other defined support operations available on an event set.
old-location: stream\ikscontrol_ksevent2.htm
old-project: stream
ms.assetid: 9e4b86cf-308f-4d9b-be28-966312dc4e43
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IKsControl, KsEvent, IKsControl::KsEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: DesktopMobile
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsControl.KsEvent
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: IKsControl
---

# IKsControl::KsEvent method



## -description
<p>The <b>IKsControl::KsEvent</b> method enables or disables an event, together with any other defined support operations available on an event set. </p>


## -syntax

````
NTSTATUS KsEvent(
   PKSEVENT Event,
   ULONG    EventLength,
   PVOID    EventData,
   ULONG    DataLength,
   ULONG    BytesReturned
);
````


## -parameters
<dl>

### -param Event 

<dd>
<p>Pointer to a <a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a> structure that describes an event to enable the event and <b>NULL</b> to disable the event.</p>
</dd>

### -param EventLength 

<dd>
<p>Specifies size, in bytes, of the buffer at <i>Event</i> when the event is enabled and zero when the event is disabled. </p>
</dd>

### -param EventData 

<dd>
<p>Pointer to a <a href="stream.kseventdata">KSEVENTDATA</a> structure that contains data for the event and buffer space that receives data for the event. </p>
</dd>

### -param DataLength 

<dd>
<p>Specifies size, in bytes, of the buffer at <i>EventData</i>. </p>
</dd>

### -param BytesReturned 

<dd>
<p>Pointer to a variable that receives the size, in bytes, of the data that <b>KsEvent</b> stores in the buffer at <i>EventData</i>. </p>
</dd>
</dl>

## -remarks
<p>To disable an event, set <i>Event</i> to <b>NULL</b>, <i>EventLength</i> to zero, and <i>EventData</i> to the pointer to the <a href="stream.kseventdata">KSEVENTDATA</a> structure that was previously used to enable the event.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
<dt>Mobile</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a>
</dt>
<dt>
<a href="stream.kseventdata">KSEVENTDATA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsControl::KsEvent method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
