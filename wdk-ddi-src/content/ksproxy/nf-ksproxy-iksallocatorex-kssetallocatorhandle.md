---
UID: NF:ksproxy.IKsAllocatorEx.KsSetAllocatorHandle
title: IKsAllocatorEx::KsSetAllocatorHandle method
author: windows-driver-content
description: Sets the handle for an allocator.
old-location: stream\iksallocatorex_kssetallocatorhandle.htm
old-project: stream
ms.assetid: E259B3D0-7536-4287-A7A2-367407D97F33
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IKsAllocatorEx, IKsAllocatorEx interface [Streaming Media Devices], KsSetAllocatorHandle method, IKsAllocatorEx::KsSetAllocatorHandle, KsSetAllocatorHandle method [Streaming Media Devices], KsSetAllocatorHandle method [Streaming Media Devices], IKsAllocatorEx interface, KsSetAllocatorHandle,IKsAllocatorEx.KsSetAllocatorHandle, ksproxy/IKsAllocatorEx::KsSetAllocatorHandle, stream.iksallocatorex_kssetallocatorhandle
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
-	IKsAllocatorEx.KsSetAllocatorHandle
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---


# KsSetAllocatorHandle method
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Sets the handle for an allocator.

## Syntax

````
HRESULT KsSetAllocatorHandle(
    
);
````

## Parameters

`AllocatorHandle`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ksproxy.h (include Ksproxy.h) |

## See Also

<a href="..\ksproxy\nn-ksproxy-iksallocatorex.md">IKsAllocatorEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsAllocatorEx::KsSetAllocatorHandle method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>