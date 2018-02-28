---
UID: NF:ksproxy.IKsPinPipe.KsGetFilterName
title: IKsPinPipe::KsGetFilterName method
author: windows-driver-content
description: Returns the name of a filter.
old-location: stream\ikspinpipe_ksgetfiltername.htm
old-project: stream
ms.assetid: A009B276-AF91-4FDD-AB81-6992311B3744
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsPinPipe, IKsPinPipe interface [Streaming Media Devices], KsGetFilterName method, IKsPinPipe::KsGetFilterName, KsGetFilterName method [Streaming Media Devices], KsGetFilterName method [Streaming Media Devices], IKsPinPipe interface, KsGetFilterName,IKsPinPipe.KsGetFilterName, ksproxy/IKsPinPipe::KsGetFilterName, stream.ikspinpipe_ksgetfiltername
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Windows
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
-	IKsPinPipe.KsGetFilterName
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsGetFilterName method
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Returns the name of a filter

## Syntax

````
HRESULT KsGetFilterName(
    
);
````

## Parameters

This function has no parameters.

## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ksproxy.h (include Ksproxy.h) |
| **Library** | ksproxy.h |

## See Also

<a href="..\ksproxy\nn-ksproxy-ikspinpipe.md">IKsPinPipe</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPinPipe::KsGetFilterName method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>