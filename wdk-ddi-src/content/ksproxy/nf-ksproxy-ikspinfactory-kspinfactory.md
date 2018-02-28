---
UID: NF:ksproxy.IKsPinFactory.KsPinFactory
title: IKsPinFactory::KsPinFactory method
author: windows-driver-content
description: The KsPinFactory method retrieves the identifier of a pin factory.
old-location: stream\ikspinfactory_kspinfactory.htm
old-project: stream
ms.assetid: 939ea77d-f194-4751-b02b-80d5e83c46f4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsPinFactory, IKsPinFactory interface [Streaming Media Devices], KsPinFactory method, IKsPinFactory::KsPinFactory, KsPinFactory method [Streaming Media Devices], KsPinFactory method [Streaming Media Devices], IKsPinFactory interface, KsPinFactory,IKsPinFactory.KsPinFactory, ksproxy/IKsPinFactory::KsPinFactory, ksproxy_80504e51-334d-4dd8-a6ce-73de9b3b3729.xml, stream.ikspinfactory_kspinfactory
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
-	IKsPinFactory.KsPinFactory
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsPinFactory method
The <b>KsPinFactory</b> method retrieves the identifier of a pin factory.

## Syntax

````
HRESULT KsPinFactory(
  [out] ULONG *PinFactory
);
````

## Parameters

`PinFactory`

Pointer to a variable that receives the identifier of the pin factory.


## Return Value

Returns NOERROR if successful; otherwise, returns an error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** | ksproxy.h |

## See Also

<a href="..\ksproxy\nn-ksproxy-ikspinfactory.md">IKsPinFactory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPinFactory::KsPinFactory method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>