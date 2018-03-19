---
UID: NF:ks.IKsControl.KsEvent
title: IKsControl::KsEvent method
author: windows-driver-content
description: The IKsControl::KsEvent method enables or disables an event, together with any other defined support operations available on an event set.
old-location: stream\ikscontrol_ksevent2.htm
old-project: stream
ms.assetid: 9e4b86cf-308f-4d9b-be28-966312dc4e43
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsControl, IKsControl interface [Streaming Media Devices], KsEvent method, IKsControl::KsEvent, KsEvent method [Streaming Media Devices], KsEvent method [Streaming Media Devices], IKsControl interface, KsEvent,IKsControl.KsEvent, avintfc_359de56d-5fcc-47ea-838c-cd110493856c.xml, ks/IKsControl::KsEvent, stream.ikscontrol_ksevent2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ks.h
req.include-header: Ks.h
req.target-type: DesktopMobile
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ks.h
api_name:
-	IKsControl.KsEvent
product: Windows
targetos: Windows
req.typenames: 
---


# KsEvent method
The <b>IKsControl::KsEvent</b> method enables or disables an event, together with any other defined support operations available on an event set.

## Syntax

````
NTSTATUS KsEvent(
   PKSEVENT Event,
   ULONG    EventLength,
   PVOID    EventData,
   ULONG    DataLength,
   ULONG    BytesReturned
);
````

## Parameters

`Event`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a> structure that describes an event to enable the event and <b>NULL</b> to disable the event.

`EventLength`

Specifies size, in bytes, of the buffer at <i>Event</i> when the event is enabled and zero when the event is disabled.

`EventData`

Pointer to a <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that contains data for the event and buffer space that receives data for the event.

`DataLength`

Specifies size, in bytes, of the buffer at <i>EventData</i>.

`BytesReturned`

Pointer to a variable that receives the size, in bytes, of the data that <b>KsEvent</b> stores in the buffer at <i>EventData</i>.


## Return Value

The <b>IKsControl::KsEvent</b> method returns the same value that would be returned if the event had been sent by IOCTL.

## Remarks

To disable an event, set <i>Event</i> to <b>NULL</b>, <i>EventLength</i> to zero, and <i>EventData</i> to the pointer to the <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that was previously used to enable the event.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | DesktopMobile |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>



<a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>