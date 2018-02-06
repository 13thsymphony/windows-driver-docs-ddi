---
UID: NF:ksproxy.IKsAllocator.KsGetAllocatorHandle
title: IKsAllocator::KsGetAllocatorHandle method
author: windows-driver-content
description: Retrieves a file handle to an allocator.
old-location: stream\iksallocator_ksgetallocatorhandle.htm
old-project: stream
ms.assetid: 9F79816F-866F-4B68-898F-87D310EFBBE7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsAllocator::KsGetAllocatorHandle, KsGetAllocatorHandle method [Streaming Media Devices], IKsAllocator interface, ksproxy/IKsAllocator::KsGetAllocatorHandle, IKsAllocator, stream.iksallocator_ksgetallocatorhandle, IKsAllocator interface [Streaming Media Devices], KsGetAllocatorHandle method, KsGetAllocatorHandle method [Streaming Media Devices], KsGetAllocatorHandle
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
-	IKsAllocator.KsGetAllocatorHandle
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsGetAllocatorHandle method
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Retrieves a file handle to an allocator.

## Syntax

````
HRESULT KsGetAllocatorHandle(
    
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

<a href="..\ksproxy\nn-ksproxy-iksallocator.md">IKsAllocator</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsAllocator::KsGetAllocatorHandle method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>