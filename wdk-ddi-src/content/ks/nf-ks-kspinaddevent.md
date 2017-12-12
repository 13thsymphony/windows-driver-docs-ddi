---
UID: NF.ks.KsPinAddEvent
title: KsPinAddEvent function
author: windows-driver-content
description: The KsPinAddEvent function adds a specified event to Pin's event list.
old-location: stream\kspinaddevent.htm
old-project: stream
ms.assetid: 1bb34062-f092-41a4-8d59-6937be7b5639
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsPinAddEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsPinAddEvent
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
---

# KsPinAddEvent function



## -description
The<b> KsPinAddEvent </b>function adds a specified event to <i>Pin</i>'s event list.



## -syntax

````
void _inline KsPinAddEvent(
  _In_ PKSPIN         Pin,
  _In_ PKSEVENT_ENTRY EventEntry
);
````


## -parameters

### -param Pin [in]

A pointer to the <a href="stream.kspin">KSPIN</a> structure to which to add a specified event.


### -param EventEntry [in]

A pointer to a <a href="stream.ksevent_entry">KSEVENT_ENTRY</a> structure describing the event to add to <i>Pin</i>.


## -returns
None


## -remarks
This function is an inline function call to <a href="stream.ksaddevent">KsAddEvent</a>.


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
Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.

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
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksaddevent">KsAddEvent</a>
</dt>
<dt>
<a href="stream.ksgenerateevents">KsGenerateEvents</a>
</dt>
<dt>
<a href="stream.ksevent_entry">KSEVENT_ENTRY</a>
</dt>
<dt>
<a href="stream.ksdefaultaddeventhandler">KsDefaultAddEventHandler</a>
</dt>
<dt><b>KsGenerateEvents</b></dt>
<dt>
<a href="stream.ksfiltergenerateevents">KsFilterGenerateEvents</a>
</dt>
<dt>
<a href="stream.kspingenerateevents">KsPinGenerateEvents</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinAddEvent function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

