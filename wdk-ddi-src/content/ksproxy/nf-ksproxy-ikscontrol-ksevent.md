---
UID: NF.ksproxy.IKsControl.KsEvent
title: IKsControl::KsEvent method
author: windows-driver-content
description: The KsEvent method enables or disables an event, along with any other defined support operations available on an event set.
old-location: stream\ikscontrol_ksevent.htm
old-project: stream
ms.assetid: b1ff6569-9568-40d8-b2a9-e63ce44720a2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IKsControl, IKsControl::KsEvent, KsEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: DesktopMobile
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsControl.KsEvent
req.alt-loc: ksproxy.h
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
---

# IKsControl::KsEvent method



## -description
The <b>KsEvent</b> method enables or disables an event, along with any other defined support operations available on an event set. 



## -syntax

````
HRESULT KsEvent(
  [in, optional] PKSEVENT Event,
  [in]           ULONG    EventLength,
  [in, out]      LPVOID   EventData,
  [in]           ULONG    DataLength,
  [in, out]      ULONG    *BytesReturned
);
````


## -parameters

### -param Event [in, optional]

Pointer to a <a href="stream.ksevent">KSEVENT</a> structure that describes an event to enable the event and <b>NULL</b> to disable the event.


### -param EventLength [in]

Size, in bytes, of the buffer at <i>Event</i> when the event is enabled and zero when the event is disabled. 


### -param EventData [in, out]

Pointer to a <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that contains data for the event and buffer space that receives data for the event. 


### -param DataLength [in]

Size, in bytes, of the buffer at <i>EventData</i>. 


### -param BytesReturned [in, out]

Pointer to a variable that receives the size, in bytes, of the data that <b>KsEvent</b> stores in the buffer at <i>EventData</i>. 


## -returns
Returns NOERROR if successful; otherwise, returns an error code. If the call succeeds, the event is on the driver's list of events.


## -remarks
To disable an event, set <i>Event</i> to <b>NULL</b>, <i>EventLength</i> to zero, and <i>EventData</i> to the pointer to the <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that was previously used to enable the event.

The <i>EventData</i> parameter of <b>IKsControl::KsEvent</b> contains a handle in <b>EventHandle.Event</b>. You can wait for the handle to become available and get notifications when the minidriver calls <b>Ks</b><i>Xxx</i><b>GenerateEvents</b> or <a href="stream.streamclassstreamnotification">StreamClassStreamNotification</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
<dt>Mobile</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksproxy.h (include Ksproxy.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksevent">KSEVENT</a>
</dt>
<dt>
<a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>
</dt>
<dt>
<a href="stream.ksfiltergenerateevents">KsFilterGenerateEvents</a>
</dt>
<dt>
<a href="stream.kspingenerateevents">KsPinGenerateEvents</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsControl::KsEvent method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

