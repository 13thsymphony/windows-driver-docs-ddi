---
UID: NF:ksproxy.IKsNotifyEvent.KsNotifyEvent
title: IKsNotifyEvent::KsNotifyEvent method
author: windows-driver-content
description: The KsNotifyEvent method requests that the KS object that owns the given DirectShow event notify the calling application with the given parameters whenever action related to the event occurs.
old-location: stream\iksnotifyevent_ksnotifyevent.htm
old-project: stream
ms.assetid: c0813b1a-402e-46ba-8d81-e31cdcbbb8dd
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsNotifyEvent, IKsNotifyEvent interface [Streaming Media Devices], KsNotifyEvent method, IKsNotifyEvent::KsNotifyEvent, KsNotifyEvent method [Streaming Media Devices], KsNotifyEvent method [Streaming Media Devices], IKsNotifyEvent interface, KsNotifyEvent,IKsNotifyEvent.KsNotifyEvent, ksproxy/IKsNotifyEvent::KsNotifyEvent, ksproxy_0fb6c49f-3aef-411d-90db-cf9a4186cdd9.xml, stream.iksnotifyevent_ksnotifyevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
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
-	ksproxy.h
api_name:
-	IKsNotifyEvent.KsNotifyEvent
product:
- Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# IKsNotifyEvent::KsNotifyEvent method
<b>DirectX 9.0 and later versions only.</b>

The <b>KsNotifyEvent</b> method requests that the KS object that owns the given DirectShow event notify the calling application with the given parameters whenever action related to the event occurs.

## Syntax

```
HRESULT KsNotifyEvent(
  ULONG     Event,
  ULONG_PTR lParam1,
  ULONG_PTR lParam2
);
```

## Parameters

`Event`

Identifies the type of DirectShow event.

`lParam1`

Specifies the first data parameter for the event.

`lParam2`

Specifies the second data parameter for the event.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="http://go.microsoft.com/fwlink/p/?linkid=183549">IMediaEvent</a>