---
UID: NF.ks.KsGenerateEvent
title: KsGenerateEvent function
author: windows-driver-content
description: The KsGenerateEvent function generates a standard event notification given an event entry structure.
old-location: stream\ksgenerateevent.htm
old-project: stream
ms.assetid: 4f142e5f-7d8a-47e0-8757-8c6e527a2472
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsGenerateEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsGenerateEvent
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: Any level (See Remarks section)
---

# KsGenerateEvent function



## -description
The <b>KsGenerateEvent</b> function generates a standard event notification given an event entry structure.


## -syntax

````
NTSTATUS KsGenerateEvent(
  _In_ PKSEVENT_ENTRY EventEntry
);
````


## -parameters

### -param EventEntry [in]

Specifies the event entry structure that references the event data. The information is used to determine what type of notification to perform. If the notification type is not one of the predefined standards, an error is returned. In the case of a single, nonrecurring event, this entry will be invalid on returning from the function. Therefore, any code that enumerates a list of events must preincrement to acquire the next event in the list before passing this event to the function.

## -returns
The <b>KsGenerateEvent</b> function returns STATUS_SUCCESS if successful, or if unsuccessful it returns an exception or memory error.

## -remarks
A device determines when event notifications are generated using the <a href="stream.ksevent_entry">KSEVENT_ENTRY</a> structure, then uses this function to perform the actual notification. <b>KsGenerateEvent</b> can be called at any IRQL. If called above DISPATCH_LEVEL, signaling of the event will be performed asynchronously in a DPC.

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
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Any level (See Remarks section)
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksfiltergenerateevents">KsFilterGenerateEvents</a>
</dt>
<dt>
<a href="stream.kspingenerateevents">KsPinGenerateEvents</a>
</dt>
<dt>
<a href="stream.kspinaddevent">KsPinAddEvent</a>
</dt>
<dt>
<a href="stream.ksfilteraddevent">KsFilterAddEvent</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGenerateEvent function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
