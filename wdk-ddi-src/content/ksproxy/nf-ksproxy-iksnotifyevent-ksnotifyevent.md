---
UID: NF:ksproxy.IKsNotifyEvent.KsNotifyEvent
title: IKsNotifyEvent::KsNotifyEvent method
author: windows-driver-content
description: The KsNotifyEvent method requests that the KS object that owns the given DirectShow event notify the calling application with the given parameters whenever action related to the event occurs.
old-location: stream\iksnotifyevent_ksnotifyevent.htm
old-project: stream
ms.assetid: c0813b1a-402e-46ba-8d81-e31cdcbbb8dd
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KsNotifyEvent method [Streaming Media Devices], IKsNotifyEvent::KsNotifyEvent, ksproxy/IKsNotifyEvent::KsNotifyEvent, KsNotifyEvent method [Streaming Media Devices], IKsNotifyEvent interface, stream.iksnotifyevent_ksnotifyevent, IKsNotifyEvent interface [Streaming Media Devices], KsNotifyEvent method, IKsNotifyEvent, KsNotifyEvent, ksproxy_0fb6c49f-3aef-411d-90db-cf9a4186cdd9.xml
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
req.lib: ksproxy.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsNotifyEvent.KsNotifyEvent
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsNotifyEvent method
<b>DirectX 9.0 and later versions only.</b>

The <b>KsNotifyEvent</b> method requests that the KS object that owns the given DirectShow event notify the calling application with the given parameters whenever action related to the event occurs.

## Syntax

````
HRESULT KsNotifyEvent(
  [in] ULONG     Event,
  [in] ULONG_PTR lParam1,
  [in] ULONG_PTR lParam2
);
````

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
| **Library** | ksproxy.h |

## See Also

<a href="http://go.microsoft.com/fwlink/p/?linkid=183549">IMediaEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsNotifyEvent::KsNotifyEvent method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>