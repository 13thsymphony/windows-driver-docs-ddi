---
UID: NF:ksproxy.IKsQualityForwarder.KsFlushClient
title: IKsQualityForwarder::KsFlushClient method
author: windows-driver-content
description: The KsFlushClient method flushes information from a pin.
old-location: stream\iksqualityforwarder_ksflushclient.htm
old-project: stream
ms.assetid: 0a1b5094-4abd-4d57-8d8c-b385fb0d46de
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsQualityForwarder, IKsQualityForwarder interface [Streaming Media Devices], KsFlushClient method, IKsQualityForwarder::KsFlushClient, KsFlushClient method [Streaming Media Devices], KsFlushClient method [Streaming Media Devices], IKsQualityForwarder interface, KsFlushClient,IKsQualityForwarder.KsFlushClient, ksproxy/IKsQualityForwarder::KsFlushClient, ksproxy_af5e225b-27b2-4b5a-a06a-1308bf5dfecd.xml, stream.iksqualityforwarder_ksflushclient
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ksproxy.h
api_name:
-	IKsQualityForwarder.KsFlushClient
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsFlushClient method
The <b>KsFlushClient</b> method flushes information from a pin.

## Syntax

````
VOID KsFlushClient(
  [in] IKsPin *Pin
);
````

## Parameters

`Pin`

Pointer to the <a href="..\ksproxy\nn-ksproxy-ikspin.md">IKsPin</a> interface for the pin from which to flush information.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** | ksproxy.h |

## See Also

<a href="..\ksproxy\nn-ksproxy-ikspin.md">IKsPin</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsQualityForwarder::KsFlushClient method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>