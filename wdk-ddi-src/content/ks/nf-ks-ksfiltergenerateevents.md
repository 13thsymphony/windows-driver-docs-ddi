---
UID: NF.ks.KsFilterGenerateEvents
title: KsFilterGenerateEvents function
author: windows-driver-content
description: The KsFilterGenerateEvents function generates events of an indicated type that are present in Filter's event list.
old-location: stream\ksfiltergenerateevents.htm
old-project: stream
ms.assetid: 62340660-3419-4da6-8d58-c2f82b4231ba
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsFilterGenerateEvents
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
req.alt-api: KsFilterGenerateEvents
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
req.irql: <=DISPATCH_LEVEL (See Remarks section.)
---

# KsFilterGenerateEvents function



## -description
The<b> KsFilterGenerateEvents</b> function generates events of an indicated type that are present in <i>Filter</i>'s event list.


## -syntax

````
void _inline KsFilterGenerateEvents(
  _In_           PKSFILTER                  Filter,
  _In_opt_ const GUID                       *EventSet,
  _In_           ULONG                      EventId,
  _In_           ULONG                      DataSize,
  _In_           PVOID                      Data,
  _In_opt_       PFNKSGENERATEEVENTCALLBACK CallBack,
  _In_opt_       PVOID                      CallBackContext
);
````


## -parameters

### -param Filter [in]

A pointer to a <a href="stream.ksfilter">KSFILTER</a> structure on which to generate events. 

### -param EventSet [in, optional]

A pointer to the event set GUID to match for determination of which events to generate. If this parameter is <b>NULL</b>, the event set GUID is not taken into account for determining matching events.

### -param EventId [in]

The event ID to match for determining which events to generate.

### -param DataSize [in]

The size of <i>Data</i> in bytes.

### -param Data [in]

A pointer to a data buffer. Specify if generating a data event.

### -param CallBack [in, optional]

A pointer to a caller-specified function that is called to determine whether a given event should be generated. If this is <b>NULL</b>, no callback verification is performed to determine whether an event should be generated (only <i>EventSet </i>and <i>EventId</i> are used). For more information, see the Remarks section below.

### -param CallBackContext [in, optional]

An optional pointer to a caller-specified context that is passed to the callback function <i>CallBack</i>. For more information, see the Remarks section below.

## -returns
None

## -remarks
When calling this function, a minidriver must place <i>Data</i> and <i>CallBackContext</i> in a locked, nonpageable data segment. In addition, note that the <i>CallBack</i> is made at DISPATCH_LEVEL. The callback function must be in a locked segment and must be prepared to run at IRQL = DISPATCH_LEVEL. Note that there is an additional issue in DX8 <i>only</i>: <i>EventSet</i> must be in a locked data segment.

This is an inline function call to <a href="stream.ksgenerateevents">KsGenerateEvents</a> that performs the necessary typecasting. Minidrivers should usually call this version instead of directly calling <b>KsGenerateEvents</b>.

An event is generated if the following conditions hold:

The event is present in <i>Filter</i>'s event list and <i>EventId</i> matches the event's ID

<i>EventSet</i> either matches the event's set GUID or is <b>NULL</b>

<i>CallBack</i> is either <b>NULL</b> or authorizes the match

<i>CallBack</i> is a caller-specified callback used for additional match determination. It is prototyped as follows:

AVStream passes the contents of the <b>KsFilterGenerateEvents</b> routine's parameter <i>CallBackContext</i> in this callback's <i>Context</i> parameter. <i>EventEntry</i> is a pointer to a <a href="stream.ksevent_entry">KSEVENT_ENTRY</a> structure that specifies the event that would be generated. The callback function should return <b>TRUE</b> if this event should be generated.

For more information, see <a href="https://msdn.microsoft.com/7add2055-8d3f-432d-8aa1-44459ac197dd">Event Handling in AVStream</a> and <a href="https://msdn.microsoft.com/3eaa1d65-8417-4a07-b358-823394baec9b">KS Events</a>. 

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
&lt;=DISPATCH_LEVEL (See Remarks section.)
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
<a href="stream.kspingenerateevents">KsPinGenerateEvents</a>
</dt>
<dt>
<a href="stream.ksevent_entry">KSEVENT_ENTRY</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsFilterGenerateEvents function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
