---
UID: NC:strmini.PHW_EVENT_ROUTINE
title: PHW_EVENT_ROUTINE
author: windows-driver-content
description: The class driver calls the stream minidriver's StrMiniEvent routine to signal to a minidriver an event should be enabled or disabled.
old-location: stream\strminievent.htm
old-project: stream
ms.assetid: 17f96498-3973-41f8-926d-85aa5f72de47
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _ZONE_DESCRIPTIOR, ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StrMiniEvent
req.alt-loc: strmini.h
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
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product: Windows 10 or later.
---

# PHW_EVENT_ROUTINE callback



## -description
The class driver calls the stream minidriver's <i>StrMiniEvent</i> routine to signal to a minidriver an event should be enabled or disabled.



## -prototype

````
PHW_EVENT_ROUTINE StrMiniEvent;

VOID StrMiniEvent(
  _In_ PHW_EVENT_DESCRIPTOR EventDescriptor
)
{ ... }
````


## -parameters

### -param EventDescriptor [in]

Describes the event, and whether it should be enabled or disabled.


## -returns
For event enable events, <i>StrMiniEvent</i> returns STATUS_SUCCESS if the event is successfully enabled, or an error code on failure. The class driver ignores the return value on disable requests.


## -remarks
The class driver queues the <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> structure it passes in <i>EventDescriptor</i>-&gt;<b>EventEntry</b>. Every other member of <i>EventDescriptor</i> is deallocated once <i>StrMiniEvent</i> exits, so any event-specific data contained in the <b>EventData</b> member of <i>EventDescriptor</i> that the minidriver needs to keep should be stored by the minidriver.

For that purpose, the minidriver can allocate space directly after the KSEVENT_ENTRY structure by providing a nonzero value in the <b>ExtraEntryData</b> member of the <a href="..\ks\ns-ks-ksevent_item.md">KSEVENT_ITEM</a> structure it used to declare the event.


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
Header

</th>
<td width="70%">
<dl>
<dt>Strmini.h (include Strmini.h)</dt>
</dl>
</td>
</tr>
</table>