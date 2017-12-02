---
UID: NF.ksproxy.IKsNotifyEvent.KsNotifyEvent
title: IKsNotifyEvent::KsNotifyEvent
author: windows-driver-content
description: The KsNotifyEvent method requests that the KS object that owns the given DirectShow event notify the calling application with the given parameters whenever action related to the event occurs.
old-location: stream\iksnotifyevent_ksnotifyevent.htm
old-project: stream
ms.assetid: c0813b1a-402e-46ba-8d81-e31cdcbbb8dd
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IKsNotifyEvent, KsNotifyEvent, IKsNotifyEvent::KsNotifyEvent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsNotifyEvent.KsNotifyEvent
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
req.iface: IKsNotifyEvent
---

# IKsNotifyEvent::KsNotifyEvent method



## -description
<p><b>DirectX 9.0 and later versions only.</b></p>
<p>The <b>KsNotifyEvent</b> method requests that the KS object that owns the given DirectShow event notify the calling application with the given parameters whenever action related to the event occurs. </p>


## -syntax

````
HRESULT KsNotifyEvent(
  [in] ULONG     Event,
  [in] ULONG_PTR lParam1,
  [in] ULONG_PTR lParam2
);
````


## -parameters
<dl>

### -param Event [in]

<dd>
<p>Identifies the type of DirectShow event. </p>
</dd>

### -param lParam1 [in]

<dd>
<p>Specifies the first data parameter for the event.</p>
</dd>

### -param lParam2 [in]

<dd>
<p>Specifies the second data parameter for the event.</p>
</dd>
</dl>

## -returns
<p>Returns NOERROR if successful; otherwise, returns an error code.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=183549">IMediaEvent</a></dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsNotifyEvent::KsNotifyEvent method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
