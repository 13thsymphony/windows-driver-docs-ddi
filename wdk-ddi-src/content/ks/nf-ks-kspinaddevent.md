---
UID: NF:ks.KsPinAddEvent
title: KsPinAddEvent function
author: windows-driver-content
description: The KsPinAddEvent function adds a specified event to Pin's event list.
old-location: stream\kspinaddevent.htm
old-project: stream
ms.assetid: 1bb34062-f092-41a4-8d59-6937be7b5639
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsPinAddEvent, KsPinAddEvent function [Streaming Media Devices], avfunc_2291126f-31dd-4e37-a082-97f24e8b5bd9.xml, ks/KsPinAddEvent, stream.kspinaddevent
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsPinAddEvent
product: Windows
targetos: Windows
req.typenames: 
---


# KsPinAddEvent function
The<b> KsPinAddEvent </b>function adds a specified event to <i>Pin</i>'s event list.

## Syntax

````
void _inline KsPinAddEvent(
  _In_ PKSPIN         Pin,
  _In_ PKSEVENT_ENTRY EventEntry
);
````

## Parameters

`Pin`

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure to which to add a specified event.

`EventEntry`

A pointer to a <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> structure describing the event to add to <i>Pin</i>.


## Return Value

None

## Remarks

This function is an inline function call to <a href="..\ks\nf-ks-ksaddevent.md">KsAddEvent</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Desktop |
| **Header** | ks.h (include Ks.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ks\nf-ks-kspingenerateevents.md">KsPinGenerateEvents</a>



<a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a>



<b>KsGenerateEvents</b>



<a href="..\ks\nf-ks-ksaddevent.md">KsAddEvent</a>



<a href="..\ks\nf-ks-ksdefaultaddeventhandler.md">KsDefaultAddEventHandler</a>



<a href="..\ks\nf-ks-ksfiltergenerateevents.md">KsFilterGenerateEvents</a>