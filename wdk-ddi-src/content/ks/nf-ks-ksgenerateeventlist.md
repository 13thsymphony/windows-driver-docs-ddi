---
UID: NF:ks.KsGenerateEventList
title: KsGenerateEventList function
author: windows-driver-content
description: The KsGenerateEventList function enumerates the event list and searches for the specified event to generate.
old-location: stream\ksgenerateeventlist.htm
old-project: stream
ms.assetid: 336dbbc1-0f3c-4a3f-b3b4-017f4d158bda
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGenerateEventList, KsGenerateEventList function [Streaming Media Devices], ks/KsGenerateEventList, ksfunc_d4a351ab-f750-4486-99ae-72c42794bee0.xml, stream.ksgenerateeventlist
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsGenerateEventList
product: Windows
targetos: Windows
req.typenames: 
---


# KsGenerateEventList function
The <b>KsGenerateEventList</b> function enumerates the event list and searches for the specified event to generate.

## Syntax

````
VOID KsGenerateEventList(
  _In_opt_ GUID              *Set,
  _In_     ULONG             EventId,
  _In_     PLIST_ENTRY       EventsList,
  _In_     KSEVENTS_LOCKTYPE EventsFlags,
  _In_     PVOID             EventsLock
);
````

## Parameters

`Set`

Specifies an optional set that the event to be generated belongs to. If present, this value is compared against the set identifier for each event in the list. If not present, the set identifiers are ignored and just the specific event identifier is used in the comparison for matching events on the list. This comparison saves time when all events are known to be contained in a single set.

`EventId`

Specifies the specific event identifier to look for on the list.

`EventsList`

Points to the head of the list of KSEVENT_ENTRY items on which the event can be found.

`EventsFlags`

Specifies the <a href="..\ks\ne-ks-ksevents_locktype.md">KSEVENTS_LOCKTYPE</a> flag specifying the exclusion lock type to be used in accessing the event list. If no flag is set, then no lock is taken.

`EventsLock`

Used to synchronize access to an element on the list. The lock is taken before enumerating the list and released after enumeration.


## Return Value

None

## Remarks

This function can be called at any IRQL level if the locking mechanism permits it.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | Any level (See Remarks section) |

## See Also

<a href="..\ks\nf-ks-kspingenerateevents.md">KsPinGenerateEvents</a>



<a href="..\ks\nf-ks-ksfilteraddevent.md">KsFilterAddEvent</a>



<a href="..\ks\nf-ks-ksfiltergenerateevents.md">KsFilterGenerateEvents</a>



<a href="..\ks\nf-ks-kspinaddevent.md">KsPinAddEvent</a>