---
UID: NF.ks.KsGenerateEventList
title: KsGenerateEventList function
author: windows-driver-content
description: The KsGenerateEventList function enumerates the event list and searches for the specified event to generate.
old-location: stream\ksgenerateeventlist.htm
old-project: stream
ms.assetid: 336dbbc1-0f3c-4a3f-b3b4-017f4d158bda
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsGenerateEventList
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
req.alt-api: KsGenerateEventList
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

# KsGenerateEventList function



## -description
The <b>KsGenerateEventList</b> function enumerates the event list and searches for the specified event to generate. 



## -syntax

````
VOID KsGenerateEventList(
  _In_opt_ GUID              *Set,
  _In_     ULONG             EventId,
  _In_     PLIST_ENTRY       EventsList,
  _In_     KSEVENTS_LOCKTYPE EventsFlags,
  _In_     PVOID             EventsLock
);
````


## -parameters

### -param Set [in, optional]

Specifies an optional set that the event to be generated belongs to. If present, this value is compared against the set identifier for each event in the list. If not present, the set identifiers are ignored and just the specific event identifier is used in the comparison for matching events on the list. This comparison saves time when all events are known to be contained in a single set.


### -param EventId [in]

Specifies the specific event identifier to look for on the list.


### -param EventsList [in]

Points to the head of the list of KSEVENT_ENTRY items on which the event can be found.


### -param EventsFlags [in]

Specifies the <a href="..\ks\ne-ks-ksevents_locktype.md">KSEVENTS_LOCKTYPE</a> flag specifying the exclusion lock type to be used in accessing the event list. If no flag is set, then no lock is taken.


### -param EventsLock [in]

Used to synchronize access to an element on the list. The lock is taken before enumerating the list and released after enumeration.


## -returns
None


## -remarks
This function can be called at any IRQL level if the locking mechanism permits it.


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGenerateEventList function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

