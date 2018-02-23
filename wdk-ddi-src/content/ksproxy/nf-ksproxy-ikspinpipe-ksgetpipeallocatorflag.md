---
UID: NF:ksproxy.IKsPinPipe.KsGetPipeAllocatorFlag
title: IKsPinPipe::KsGetPipeAllocatorFlag method
author: windows-driver-content
description: Not recommended for application use.
old-location: stream\ikspinpipe_ksgetpipeallocatorflag.htm
old-project: stream
ms.assetid: EBF5B615-A7B1-4B44-855C-7956334AAF75
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KsGetPipeAllocatorFlag, IKsPinPipe interface [Streaming Media Devices], KsGetPipeAllocatorFlag method, IKsPinPipe, stream.ikspinpipe_ksgetpipeallocatorflag, IKsPinPipe::KsGetPipeAllocatorFlag, KsGetPipeAllocatorFlag method [Streaming Media Devices], KsGetPipeAllocatorFlag method [Streaming Media Devices], IKsPinPipe interface, ksproxy/IKsPinPipe::KsGetPipeAllocatorFlag
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsPinPipe.KsGetPipeAllocatorFlag
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsGetPipeAllocatorFlag method
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Not recommended for application use.

## Syntax

````
HRESULT KsGetPipeAllocatorFlag(
    
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPinPipe::KsGetPipeAllocatorFlag method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>