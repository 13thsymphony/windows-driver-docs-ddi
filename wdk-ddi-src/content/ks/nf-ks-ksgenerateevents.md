---
UID: NF:ks.KsGenerateEvents
title: KsGenerateEvents function
author: windows-driver-content
description: The KsGenerateEvents function generates events of an indicated type that are present in Object's event list.
old-location: stream\ksgenerateevents.htm
old-project: stream
ms.assetid: 3c96012f-8307-417c-be8f-bb466c576669
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGenerateEvents, KsGenerateEvents function [Streaming Media Devices], avfunc_47306d1b-67f9-4ea6-81bb-3b76b848667a.xml, ks/KsGenerateEvents, stream.ksgenerateevents
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsGenerateEvents
product: Windows
targetos: Windows
req.typenames: 
---


# KsGenerateEvents function
The<b> KsGenerateEvents</b> function generates events of an indicated type that are present in <i>Object</i>'s event list.

## Syntax

````
void KsGenerateEvents(
  _In_           PVOID                      Object,
  _In_opt_ const GUID                       *EventSet,
  _In_           ULONG                      EventId,
  _In_           ULONG                      DataSize,
  _In_opt_       PVOID                      Data,
  _In_opt_       PFNKSGENERATEEVENTCALLBACK CallBack,
  _In_opt_       PVOID                      CallBackContext
);
````

## Parameters

`Object`

The object on which to generate events. This can be an AVStream filter or pin object.

`EventSet`

The event set GUID to match to determine which events to generate. If this parameter is <b>NULL</b>, set GUID is not taken into account for determining matching events.

`EventId`

The event ID to match to determine which events to generate.

`DataSize`

The size in bytes of the data with which to generate the data event.

`Data`

A pointer to a data buffer to include in the event notification. If the driver does not need to convey additional information via the notification, set this optional parameter to <b>NULL</b>.

`CallBack`

A pointer to a caller-specified function that is called to determine whether a given event should be generated. If this is <b>NULL</b>, no callback verification is performed to determine whether an event should be generated (only <i>EventSet </i>and <i>EventId</i> are used).

`CallBackContext`

A pointer to a caller-specified context that is passed to the callback function <i>CallBack</i>.


## Return Value

None

## Remarks

When calling this function, a minidriver must place <i>Data</i> and <i>CallBackContext</i> in a locked, nonpageable data segment. In addition, note that the <i>CallBack</i> is made at DISPATCH_LEVEL. The callback function must be in a locked segment and must be prepared to run at IRQL = DISPATCH_LEVEL. Note that there is an additional issue in DX8 <i>only</i>: <i>EventSet</i> must be in a locked data segment.

Minidrivers typically do not call this function directly and instead use one of the versions that performs appropriate casting: <a href="..\ks\nf-ks-ksfiltergenerateevents.md">KsFilterGenerateEvents</a> or <a href="..\ks\nf-ks-kspingenerateevents.md">KsPinGenerateEvents</a>.

An event is generated if it is present in <i>Object's </i>event list and <i>EventId </i>matches the event's ID, <i>EventSet</i> either matches the event's set GUID or is <b>NULL</b>, and <i>CallBack </i>is either <b>NULL</b> or authorizes the match.

<i>CallBack</i> is a caller-specified callback used for additional match determination. It is prototyped as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN CallBack (IN PVOID Context, IN PKSEVENT_ENTRY EventEntry);</pre>
</td>
</tr>
</table></span></div>
AVStream passes the contents of the <b>KsGenerateEvents</b> routine's parameter <i>CallBackContext</i> in this callback's <i>Context</i> parameter. <i>EventEntry</i> is a pointer to a <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> structure that specifies the event that would be generated. The callback function should return <b>TRUE</b> if this event should be generated.

For more information, see <a href="https://msdn.microsoft.com/7add2055-8d3f-432d-8aa1-44459ac197dd">Event Handling in AVStream</a> and <a href="https://msdn.microsoft.com/3eaa1d65-8417-4a07-b358-823394baec9b">KS Events</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ks\nf-ks-kspingenerateevents.md">KsPinGenerateEvents</a>



<a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a>



<a href="..\ks\nf-ks-ksfiltergenerateevents.md">KsFilterGenerateEvents</a>



<a href="..\ks\nf-ks-ksaddevent.md">KsAddEvent</a>