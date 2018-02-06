---
UID: NF:ksproxy.IKsAllocator.KsSetAllocatorMode
title: IKsAllocator::KsSetAllocatorMode method
author: windows-driver-content
description: Sets the mode in which an allocator allocates memory.
old-location: stream\iksallocator_kssetallocatormode.htm
old-project: stream
ms.assetid: 8F64E58D-9C04-43BA-9C1B-88AD081176A9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsAllocator interface [Streaming Media Devices], KsSetAllocatorMode method, KsSetAllocatorMode method [Streaming Media Devices], ksproxy/IKsAllocator::KsSetAllocatorMode, IKsAllocator::KsSetAllocatorMode, KsSetAllocatorMode method [Streaming Media Devices], IKsAllocator interface, IKsAllocator, KsSetAllocatorMode, stream.iksallocator_kssetallocatormode
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
-	IKsAllocator.KsSetAllocatorMode
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsSetAllocatorMode method
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Sets the mode in which an allocator allocates memory.

## Syntax

````
HRESULT KsSetAllocatorMode(
    
);
````

## Parameters

`Mode`




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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsAllocator::KsSetAllocatorMode method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>