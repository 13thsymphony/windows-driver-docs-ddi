---
UID : NF:ksproxy.IKsControl.KsEvent
title : IKsControl::KsEvent method
author : windows-driver-content
description : The KsEvent method enables or disables an event, along with any other defined support operations available on an event set.
old-location : stream\ikscontrol_ksevent.htm
old-project : stream
ms.assetid : b1ff6569-9568-40d8-b2a9-e63ce44720a2
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : IKsControl, IKsControl::KsEvent, KsEvent
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : ksproxy.h
req.include-header : Ksproxy.h
req.target-type : DesktopMobile
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IKsControl.KsEvent
req.alt-loc : ksproxy.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : PIPE_STATE
---


# KsEvent method
The <b>KsEvent</b> method enables or disables an event, along with any other defined support operations available on an event set.

## Syntax

````
HRESULT KsEvent(
  [in, optional] PKSEVENT Event,
  [in]           ULONG    EventLength,
  [in, out]      LPVOID   EventData,
  [in]           ULONG    DataLength,
  [in, out]      ULONG    *BytesReturned
);
````

## Parameters

`Event`

Pointer to a <a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a> structure that describes an event to enable the event and <b>NULL</b> to disable the event.

`EventLength`

Size, in bytes, of the buffer at <i>Event</i> when the event is enabled and zero when the event is disabled.

`EventData`

Pointer to a <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that contains data for the event and buffer space that receives data for the event.

`DataLength`

Size, in bytes, of the buffer at <i>EventData</i>.

`BytesReturned`

Pointer to a variable that receives the size, in bytes, of the data that <b>KsEvent</b> stores in the buffer at <i>EventData</i>.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code. If the call succeeds, the event is on the driver's list of events.

## Remarks

To disable an event, set <i>Event</i> to <b>NULL</b>, <i>EventLength</i> to zero, and <i>EventData</i> to the pointer to the <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that was previously used to enable the event.

The <i>EventData</i> parameter of <b>IKsControl::KsEvent</b> contains a handle in <b>EventHandle.Event</b>. You can wait for the handle to become available and get notifications when the minidriver calls <b>Ks</b><i>Xxx</i><b>GenerateEvents</b> or <a href="..\strmini\nf-strmini-streamclassstreamnotification.md">StreamClassStreamNotification</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | DesktopMobile |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a>
</dt>
<dt>
<a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfiltergenerateevents.md">KsFilterGenerateEvents</a>
</dt>
<dt>
<a href="..\ks\nf-ks-kspingenerateevents.md">KsPinGenerateEvents</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsControl::KsEvent method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>