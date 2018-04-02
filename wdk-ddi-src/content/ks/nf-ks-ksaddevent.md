---
UID: NF:ks.KsAddEvent
title: KsAddEvent function
author: windows-driver-content
description: The KsAddEvent function adds an event to Object's event list.
old-location: stream\ksaddevent.htm
old-project: stream
ms.assetid: 75c909b1-8eb5-4887-b528-d3ac465ee12b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsAddEvent, KsAddEvent function [Streaming Media Devices], avfunc_20b264e1-c7ad-4b24-bff3-996b9d478a44.xml, ks/KsAddEvent, stream.ksaddevent
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsAddEvent
product:
- Windows
targetos: Windows
req.typenames: 
---


# KsAddEvent function
The<b> KsAddEvent </b>function adds an event to <i>Object</i>'s event list.

## Syntax

```
void KsAddEvent(
  PVOID          Object,
  PKSEVENT_ENTRY EventEntry
);
```

## Parameters

`Object`

The object to which to add the event.

`EventEntry`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a> structure describing the event to add to <i>Object</i>.


## Return Value

None

## Remarks

Minidrivers typically do not call this routine directly; instead, they use <a href="https://msdn.microsoft.com/library/windows/hardware/ff562525">KsFilterAddEvent</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563490">KsPinAddEvent</a>. 

After events have been added to the event list, these events can be generated as data events by a <b>Ks</b><i>Xxx</i><b>GenerateEvents</b> call. Typecasting of the object (a filter or pin) to PVOID must be provided by the caller.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.  |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561662">KsDefaultAddEventHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562525">KsFilterAddEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562597">KsGenerateEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563490">KsPinAddEvent</a>